Mikrotik adalah sebuah perusahaan Latvia yang didirikan pada tahun 1996. Perusahaan tersebut memproduksi perangkat jaringan seperti router. RouterOS adalah sistem operasi (OS) berbasis kernel Linux yang menjadi OS untuk perangkat jaringan dari Mikrotik. RouterOS dapat berjalan baik pada perangkat keras maupun*virtual machine*, serta itu dapat diakses dan diatur menggunakan program WinBox, yang tersedia untuk OS Windows.    
Langkah-langkah mengatur router Mikrotik (sesuai dengan *subbab 3.6.1*):     
1. Hubungkan satu sisi kabel Ethernet dengan salah satu port Ethernet pada router Mikrotik, dan hubungkan sisi lain kabel Ethernet dengan port Ethernet pada desktop.
2. Ulangi langkah di atas hingga ketiga desktop tersebut disambungkan dengan router Mikrotik menggunakan kabel Ethernet.
3. Setelah itu, hidupkan desktop Windows yang sudah terhubung dengan router Mikrotik tersebut, dan jalankan program Control Panel.
4. Setelah jendela Control Panel muncul, klik “view network status and task" yang berada di bawah "Network and Internet."
5. Setelah jendela Network and Sharing Center muncul, klik “Change adapter settings.”
6. Setelah jendela Network Connections muncul, klik-kanan “Ethernet”, dan setelah sebuah menu muncul, klik “Properties.”
7. Setelah jendela Ethernet Properties muncul, klik “Internet Protocol Version 4 (TCP/IPv4)” kemudian klik “Properties.”
8. Setelah jendela Internet Protocol Version 4 (TCP/IPv4) Properties muncul, isikan “192.168.1.10,” “192.168.1.20,” atau “192.1681.30” (pilih hanya salah satu untuk masing-masing desktop) pada baris “IP address,” kemudian klik baris “Subnet mask” supaya subnet mask terisi otomatis, isikan “192.168.1.1” pada baris “Default gateway,” dan isikan "1.1.1.1" pada baris Preferred DNS server dan isikan "1.0.0.1" pada baris Alternate DNS server; setelah selesai, klik “OK.”
9. Ulangi langkah 3–8 untuk setiap desktop.
10. Setelah itu, jalankan program WinBox pada salah satu desktop untuk mengakses dan mengkonfigurasi router Mikrotik tersebut.
11. Setelah berhasil log-masuk, klik menu “Bridge”; setelah jendela Bridge muncul, klik tanda tambah berwarna biru.
12. Setelah jendela New Interface muncul, ganti nama pada baris “Name” (jika ingin), kemudian klik “OK” untuk menambahkan antarmuka bridge tersebut.
13. Setelah jendela New Interface menghilang dan item bridge yang ditambahkan sudah muncul, klik tab “Ports.”
14. Pada tab “Ports,” klik tanda tambah berwarna biru; setelah jendela New Bridge Port muncul, pilih "ether2" pada baris Interface dan pilih bridge1 pada baris Bridge; setelah selesai, klik "OK."
15. Ulangi langkah 14, tetapi untuk "ether3" dan "ether4."
16. Selanjutnya, klik menu “IP” => “Addresses”; setelah jendela Address List muncul, klik tanda tambah; setelah jendela New Address muncul, isikan "192.168.1.1/24" pada baris Address, dan pilih “bridge1” pada baris Interface; setelah selesai, klik “OK.”  
17. Untuk mengetahui informasi tentang konfigurasi jaringan saat ini, jalankan Command Prompt atau PowerShell, dan ketikan “ipconfig” kemudian klik tombol "Enter".
18. Sekarang bisa gunakan "ping" untuk mengetahui konektivitas antara sesama desktop, atau desktop dengan router, dalam LAN ini.
19. Jika ping tersebut berhasil, maka langkah-langkah ini sukses. Sekarang, secara opsional, LAN ini bisa dihubungkan ke Internet.   
20. Dalam langkah-langkah ini, karena sebuah sebab, router menerima akses Internet secara nirkabel.  
21. Pertama, klik menu “Wireless” dalam WinBox; setelah jendela Wireless Tables muncul, pada tab Wi-Fi Interface, klik item wlan1 kemudian klik tanda centang.   
22. Setelah itu, klik dua kali item wlan1 tersebut; setelah jendela Interface \<wlan1> muncul, klik “Scan...”; setelah jendela Scanner muncul, klik "Start"; setelah muncul beberapa SSID, klik salah satu yang akan digunakan kemudian klik "Connect"; setelah selesai, klik "OK."  
23. Setelah jendela Scanner menghilang, klik "OK" pada jendela Interface \<wlan1>; setelah jendela tersebut menghilang, tanda "R" di sebelah "wlan1" pada Wireless Tables akan muncul jika router berhasil terkoneksi dengan perangkat yang memancarkan sinyal Wi-Fi tersebut.   
24. Selanjutnya, setelah tanda "R" tersebut muncul, klik menu “IP” => “DHCP Client.”   
25. Setelah jendela DHCP Client muncul, klik tanda tambah; setelah jendela New DHCP Client muncul, pilih "wlan1" pada baris Interface; setelah selesai, klik "OK."  
26. Setelah jendela New DHCP Client menghilang, pada jendela DHCP Client, seharusnya item "wlan1" muncul, dan jika berhasil, maka "bound" akan muncul pada kolom Status pada item tersebut.  
27. Terakhir, NAT (network address translation) harus diatur. Klik menu “IP” => “Firewall”; setelah jendela Firewall muncul, klik tab "NAT."   
28. Pada tab NAT, klik tanda tambah; setelah jendela NAT Rule <> muncul, isikan seperti berikut ini: Dalam tab General, pilih "scrnat" pada baris Chain, dan pilih "wlan1"; dalam tab Action, pilih "masquerade" pada baris Action. Setelah selesai, klik "OK."    
29. Sekarang, secara teori, langkah-langkah ini sudah selesai, dan LAN ini sudah terhubung ke Internet. Namun, untuk memastikan bahwa LAN ini memang benar-benar terhubung ke Internet, jalankan peramban web dan buka situs web apa saja—misalnya [https://google.com/](https://google.com/) atau [https://fast.com/](https://fast.com/) atau [https://youtube.com/](https://youtube.com/)—kemudian jika situs web tersebut terbuka, maka LAN ini memang sudah terhubung ke Internet. 
