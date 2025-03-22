# BPJS Fingerprint BOT

Rest API Untuk membuka aplikasi sidik jari BPJS. Digunakan untuk implementasi APM (Anjungan Pendaftaran mandiri) berbasis WEB.

## Build

untuk membuat exe

```bash
go build -o FingerprintBot.exe main.go
```

letakkan file exe ini di folder instalasi. sejajar dengan file 'After.exe'

## Dokumentasi Rest API

Ping

```bash
curl --location --request POST 'http://localhost:3005/ping'
```

membuka aplikasi

```bash
curl --location 'http://localhost:3005/open' \
--header 'Content-Type: application/json' \
--data-raw '{
"username": "agung,arief",
"password": "Agung123#",
"no_bpjs": "0003498723872394",
"app_login_time": 1500 // default 1000. format milisecond
}'
```

menutup aplikasi

```bash
curl --location 'http://localhost:3005/close' \
--header 'Content-Type: application/json' \
--data '{
}'
```