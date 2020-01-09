

Kubernetes adalah platform luas untuk mengelola kluster penampung, yang berasal dari Google. Seperti kebanyakan perangkat lunak server dari Google, Kubernetes unggul dalam skalabilitas.

update repo #sudo apt-get update

update certificate #sudo apt-get apt install apt-transport-https ca-certificates curl software-properties-common -y

tambahkan key untuk kubernetes #curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -

tambahkan repo kubernetes #cat </etc/apt/sources.list.d/kubernetes.list deb http://apt.kubernetes.io/ kubernetes-xenial main EOF

update repo kembali #sudo apt-get update

install kubernetes #apt install kubelet kubeadm kubernetes-cni -y

setup Kubernetes Master #sysctl net.bridge.bridge-nf-call-iptables=1

disable swap #swapoff -a

inisialisasi kubernetes #kubeadm init --pod-network-cidr=10.244.0.0/16 --apiserver-advertise-address=192.168.88.100 --kubernetes-version stable-1.9

Jika berhasil maka akan muncul output seperti berikut. Your Kubernetes master has initialized successfully!

Men-deploy Aplikasi Golang ke Kubernetes

membuat project laravel #composer create-project --prefer-dist laravel/laravel my_app

menjalankan project laravel #php artisan serve

menggunakan docker compose #sudo apt-get install -y docker.io docker-compose

membuat dua file menggunakan docker file #app.dockerfile, web.dockerfile

buat file yml #docker-compose.yml

atur laravel conf #laravelVHost.conf

atur env laravel #atur file .env

jalankan docker compose #docker-compose up -d

kemudian akses #http://localhost:8080

lakukan migrate #php artisan migrate
