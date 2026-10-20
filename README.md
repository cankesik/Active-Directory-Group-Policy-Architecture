# Active-Directory-Group-Policy-Architecture
Çok Şubeli Kurumsal Active Directory, Delegasyon, GPO Kısıtlamaları ve Script Otomasyonu Projesi
# 🏢 Enterprise Active Directory & Group Policy Architecture

![Windows Server](https://img.shields.io/badge/Windows%20Server-2022-blue)
![Active Directory](https://img.shields.io/badge/Active%20Directory-AD%20DS-green)
![Security](https://img.shields.io/badge/Security-GPO%20%26%20Delegation-red)

Bu depo, çok şubeli bir kurumsal yapının (**Ankara** ve **Bursa** şubeleri) **Active Directory Domain Services (AD DS)** hiyerarşisini, yetkilendirme (**Delegation of Control**), erişim kısıtlamalarını (**Logon Hours & GPO Restrictions**), interaktif oturum politikalarını ve **VBScript** otomasyon senaryolarını içermektedir.

---

## 📁 Depo İçeriği

* [`/docs`](./docs): Projenin tam PDF raporu ve mimari akış şeması.
* [`/scripts`](./scripts): GPO üzerinden istemcilere dağıtılan VBScript otomasyon kodları.
* [`/screenshots`](./screenshots): ADUC, GPO Editor ve istemci tarafındaki doğrulama ekran görüntüleri.

---

## 📌 Proje Özet Mimarisi

* **Domain Name:** `can.com`
* **Domain Controllers:** `DC1` (Primary DC) ve `ADDC` (Additional DC - High Availability)
* **Lokasyonlar & OU Yapısı:** Ankara & Bursa Şubeleri (`SATIS`, `YONETIM`, `BILGISAYARLAR`)
* **Güvenlik Mimarisi:** Custom GPO, Delegation of Control, Logon Hours, Interactive Banner

---

## ⚙️ Uygulanan Yapılandırmalar

1. **Delegation of Control:** `Principle of Least Privilege` uyarınca `ankaraadmin1` kullanıcısına Ankara OU'sunda nesne yönetimi yetkisi devredilmiştir.
2. **Logon Hours:** `as2` kullanıcısı için mesai dışı ve tatil günlerinde oturum engellenmiştir.
3. **Interactive Logon Banner:** Giriş öncesi yasal uyarı banner'ı (`MERHABA` / `ŞİRKETİMİZE HOŞ GELDİNİZ...`) aktif edilmiştir.
4. **Script Otomasyonu:** Şube bazlı oturum açılışlarında çalışan VBScript yapıları kurgulanmıştır.

---

## 🚀 Gelecek Fazlar (Roadmap)

- [x] Faz 1: AD DS, OU Hierarchy, Delegation, GPO & Scripting
- [ ] Faz 2: LAPS (Local Administrator Password Solution) Entegrasyonu
- [ ] Faz 3: BitLocker & Central Recovery Key Management
- [ ] Faz 4: Event Log Forwarding & Security Auditing
