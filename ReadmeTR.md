# Bitz Miner CLI Rehberi (Eclipse Ağı Üzerinde)

# Bitz Nedir?
- Eclipse ağında herkesin madencilik yapabileceği ilk ePOW emtia token’ıdır.
- Maksimum arz: 5 milyon.
- Ön madencilik YOK, Takım veya içeriden biri için sıfır tahsis.
- Token adresi: https://eclipsescan.xyz/token/64mggk2nXg6vHC1qCdsZdEFzd5QGN4id54Vbho4PswCF

# GEREKLİLER
- ETH yüklü Eclipse cüzdanı (örneğin: Backpack)
- Basit CPU sistem ya da VPS. (VPS satın alma ve kurulum rehberi: https://github.com/0xmoei/Linux_Node_Guide)
- Linux Ubuntu terminali
- Windows kullanıcıları: WSL üzerinden Ubuntu kurmalı (https://github.com/0xmoei/Install-Linux-on-Windows)

## 1. Paket Kurulumu
```bash
sudo apt-get update && sudo apt-get upgrade -y
sudo apt install screen curl nano -y
```
## 2. Rust Kurulumu
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
## Kurulum ekranında “1” yazıp Enter’a bas
```bash
source $HOME/.cargo/env
```
## 3. Solana CLI Kurulumu
```bash
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```
## Terminali kapatıp tekrar aç
```bash
solana version
```

## 4. RPC Ayarı
```bash
solana config set --url https://mainnetbeta-rpc.eclipse.xyz/
```
## CÜZDAN OLUŞTURMA
```bash
solana-keygen new
```
#### Şifre koyabilir ya da Enter diyerek geçebilirsin
#### Seed phrase ve Public Key’i güvenli bir yere kaydet

## PRIVATE KEY ALMA
```bash
solana config get
```
#### Burada çıkan yol senin key dosyan: ~/.config/solana/id.json
```bash
cat ~/.config/solana/id.json
```
#### Bu JSON array senin private key’in, mutlaka kaydet

#### PRIVATE KEY’İ BACKPACK CÜZDANA IMPORT ET
#### Sonra bu cüzdana Eclipse ağı üzerinden ETH gönder

## BITZ KURULUMU
```bash
cargo install bitz
```
## BITZ MADENCİ ÇALIŞTIRMA
```bash
screen -S bitz
```
```bash
bitz collect
```
#### NOT: Varsayılan olarak 1 çekirdek kullanır. Daha fazla çekirdek için:
#### (Örneğin sistemin 8 çekirdekliyse)
```bash
bitz collect --cores 8
```
## SCREEN KOMUTLARI
#### Arka plana al: Ctrl+A+D
#### Geri dön: screen -r bitz
#### Screen listesi: screen -ls
#### Screen kapat: screen -XS bitz quit

## FAYDALI KOMUTLAR (Screen dışında çalıştırılır)
- bitz account        # Hesap bilgisi görüntüle
- bitz claim          # Kazanılan Bitz’i cüzdana çek
- bitz -h             # Tüm komutları göster

#### BAŞARIYLA MADENCİ ÇALIŞIYOR OLACAK
#### Ekranda başarıyla çalıştığını gösteren bilgi gelecektir.
