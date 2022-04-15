## Jenkins Credential

- Tambahkan credential baru

<p align="center"><img src="../week-3/assets/Jenkins-Job/1.png"></p>

- masukkan private key kedalam credential

<p align="center"><img src="../week-3/assets/Jenkins-Job/2.png"></p>

<p align="center"><img src="../week-3/assets/Jenkins-Job/3.png"></p>

## Jenkins Pipeline Job

- Buat job baru dengan pilihan pipeline

<p align="center"><img src="../week-3/assets/Jenkins-Job/4.png"></p>

- centang bagian `GitHub hook trigger for GITScm polling` agar dapat melakukan webhook

<p align="center"><img src="../week-3/assets/Jenkins-Job/5.png"></p>

- pilih `Pipeline script from SCM`
- SCM pilih Git
- masukkan url repositori github
- pilih credential
- masukkan branch yang ingin kita build

<p align="center"><img src="../week-3/assets/Jenkins-Job/6.png"></p>

- pada Script Path masukkna nama file script pipeline yang ingin kita buat. Untuk mempermudah beri nama `Jenkinsfile`. Kemudian apply dan save

<p align="center"><img src="../week-3/assets/Jenkins-Job/7.png"></p>

- buat file Jenkinsfile pada direktori aplikasi yang ingin kita deploy

```
def secret = 'server'
def server = 'ubuntu@10.224.143.122'
def dir = 'dumbflix-frontend'
def branch = 'master'

pipeline{
	agent any
	stages{
		stage ('Delete container and images & git pull'){
			steps{
				sshagent([secret]) {
					sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
					cd ${dir}
					docker-compose down 
					docker system prune -f
					git pull origin ${branch}
					exit
					EOF"""
				}
			}
		}
	stage ('Build Images'){
                        steps{
                                sshagent([secret]) {
                                        sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
                                        cd ${dir}/nginx
					docker build -t nginx:re .
					cd ..
                                        docker-compose build
                                        exit
                                        EOF"""
                                }
                        }
                }
	stage ('Deploy Container'){
                        steps{
                                sshagent([secret]) {
                                        sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
                                        cd ${dir}
                                        docker-compose up -d
                                        exit
                                        EOF"""
                                }
                        }
                }

	}
}
```

- Setelah membuat Jenkinsfile lakukan push ke dalam repositori Github
- Jalankan Build Now dan aplikasi sudah terdeploy secara otomatis tanpa masuk kedalam server

<p align="center"><img src="../week-3/assets/Jenkins-Job/8.png"></p>

## Webhook

Webhook adalah suatu sistem yang ketika ada perubahan pada repositori github maka url https yang dituju akan tertrigger/berjalan otomatis melakukan deploy. Pada bagian ini karena saya tidak memiliki public host maka saya menggunakan ngrok tunnel agar dapat mengenerate https.

- Install ngrok pada server ci/cd jenkins

`snap install ngrok`

- Connect akun ngrok menggunakan token

`ngrok config add-authtoken 26uCNXCqVRZyS6P2P77A9cQD2rE_33McENVsXnsbNV19KAeGb`

- generate https jenkins 8080

`ngrok http 8080`

<p align="center"><img src="../week-3/assets/Jenkins-Job/17.png"></p>

- login jenkins menggunakan alamat https yang sudah dibuat

<p align="center"><img src="../week-3/assets/Jenkins-Job/18.png"></p>

- Buka repositori github. pilih menu setting lalu webhook.
- pilih add webhook

<p align="center"><img src="../week-3/assets/Jenkins-Job/19.png"></p>

- masukkan url https kedalam `Payload URL` dan tambahkan `/github-webhook/`

<p align="center"><img src="../week-3/assets/Jenkins-Job/20.png"></p>

- Webhook berhasil diterapkan

<p align="center"><img src="../week-3/assets/Jenkins-Job/21.png"></p>
