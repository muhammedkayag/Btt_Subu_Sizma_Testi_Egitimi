# Sızma Testi 101 - Kurulum Rehberi


## 1. VirtualBox Kurulumu
- VirtualBox indirip kurmanız gerekiyor.  
İndirme linki: [VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)

Kurulum sırasında herhangi bir ayarı değiştirmeden Next → Next → Finish adımlarını takip edebilirsiniz.

---

## 2. Parrot Security OS (Pentest Makinesi)

Parrot, saldırı makinesi olarak kullanılacaktır.  

### İndirme:
[Parrot Security 6.4 OVA](https://deb.parrot.sh/parrot/iso/6.4/Parrot-security-6.4_amd64.ova)

### Kurulum Videosu:
[YouTube: Parrot OS VirtualBox Kurulumu](https://www.youtube.com/watch?v=6ggzRmh9f5U)

### VirtualBox’a Ekleme:
- VirtualBox aç → `File > Import Appliance` seç → `.ova` dosyasını göster.
- “Next → Import” adımlarını takip edin.
- İşlem tamamlandığında sanal makine listesinde Parrot Security görünecek.

---

## 3. Hedef Makineler

Bu makineler, saldırı pratikleri için kullanılacaktır.

### Vulnhub: Basic Pentesting
- [İndirme Linki (Vulnhub)](https://download.vulnhub.com/basicpentesting/basic_pentesting_1.ova)
- `.ova` dosyasını indirip VirtualBox’a import edin.

### BTT CTF
- [İndirme Linki (Google Drive)](https://drive.google.com/file/d/1TKW6-fOt3DqpyuK9TXpI-AjEH4vcW2PT/view?usp=drive_link)
- İndirilen `.ova` dosyasını VirtualBox’a ekleyin (`File > Import Appliance`).


---

## 4. Ağ Ayarları

Tüm makineler aynı ağda çalışabilmesi için **Bridge Adapter (Köprü Ağı)** kullanılmalıdır.  

Ayarlar:
1. VirtualBox'ta ilgili sanal makineyi seçin → Settings → Network
2. Attached to: **Bridged Adapter**
3. Adım 1-2'yi tüm makineler için uygulayın.

Bu şekilde hem ana bilgisayar hem de tüm sanal makineler aynı yerel ağda bulunur.  
Eğitime başlamadan önce sanal makinelerin birbirini görebildiğini kontrol ediniz.  

Terminalden test:
```bash
ping <hedef-makine-ip>
