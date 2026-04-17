# การติดตั้งและใช้งาน Nunchuk Wallet

# 1. เกี่ยวกับ Nunchuk Wallet
**Nunchuk Wallet** เป็น Bitcoin Wallet ที่เน้นความปลอดภัยในระดับสถาบัน (Institutional Grade) โดยเฉพาะเรื่องการทำ **Multisig** และการวางแผนมรดก (Inheritance planning) มีจุดเด่นคือการรองรับอุปกรณ์ hardware wallet ที่หลากหลาย และรองรับการทำงานแบบ Air-gapped (NFC/QR/SD Card) ได้อย่างสมบูรณ์แบบ มีฟีเจอร์เด่นดังนี้:

*   **Multisig Focus:** ออกแบบมาเพื่อการทำ Multi-signature ที่ง่ายและปลอดภัยที่สุดในตลาด
*   **Air-gapped Support:** รองรับการเชื่อมต่อกับ Hardware Wallet ผ่าน NFC และ QR Code (เช่น Coldcard, Keystone)
*   **Inheritance Protocol:** มีระบบที่ช่วยให้ทายาทสามารถเข้าถึงเหรียญได้ตามเงื่อนไขที่กำหนดไว้อย่างปลอดภัย
*   **Privacy & Security:** รองรับการต่อผ่าน Node ของตัวเอง และมีการเข้ารหัสข้อมูลในเครื่องอย่างหนาแน่น

> **[ ⚠️ สำคัญ!!! ]** Nunchuk Wallet เป็นซอฟต์แวร์ที่มีให้ใช้งานทั้งบน Desktop และ Mobile ซึ่งในกรณีของ Mobile สามารถดาวน์โหลดได้จาก App Store และ Google Play Store แต่สำหรับการเรียนการสอนในคลาสนี้ของเราจะเน้นการใช้งาน **Nunchuk Desktop** เป็นหลัก แต่หากสนใจติดตั้ง Nunckuk Mobile ด้วยสามารถติดตั้งได้ที่:
>*   **Android:** [Google Play Store](https://play.google.com/store/apps/details?id=io.nunchuk.android)
>*   **iOS:** [Apple App Store](https://apps.apple.com/us/app/nunchuk-bitcoin-wallet/id1563190073)

> ช่องทางประชาสัมพันธ์อย่างเป็นทางการของ Nunchuk Wallet
> * Website: [nunchuk.io](https://nunchuk.io/)
> * Github: [nunchuk-io](https://github.com/nunchuk-io)
> * X: [nunchuk_io](https://x.com/nunchuk_io)

ปัจจุบันที่เขียนคู่มือนี้ (เมษายน 2026) Nunchuk Desktop เวอร์ชั่นล่าสุดคือ `2.4.0`

# 2. การดาวน์โหลดและตรวจสอบ

เพื่อให้มั่นใจว่าซอฟต์แวร์ที่ดาวน์โหลดมานั้นเป็นซอฟต์แวร์ของแท้จากนักพัฒนาตัวจริง และไม่ถูกดัดแปลงแก้ไขโดยผู้ประสงค์ร้าย เราจำเป็นต้องดาวน์โหลดจากแหล่งที่มาทางการ และตรวจสอบความถูกต้องของซอฟต์แวร์ก่อนการติดตั้ง

## 2.1 ดาวน์โหลดไฟล์ที่จำเป็น

ไปที่หน้า [Releases บน Github](https://github.com/nunchuk-io/nunchuk-desktop/releases) ควรสร้างโฟลเดอร์ใหม่แยกต่างหากและดาวน์โหลดไฟล์ทั้ง 3 รายการนี้มาไว้ในโฟลเดอร์เดียวกัน:
1.  **ไฟล์ .zip:** ตาม OS ของคุณ
2.  **SHA256SUMS.asc:** ไฟล์รายการค่า hash ของไฟล์ .zip สำหรับทุก OS ซึ่งนักพัฒนาได้ลงลายเซ็นดิจิทัลกํากับไว้แล้ว

## 2.2 ตรวจสอบความถูกต้อง

### 2.2.1 เช็คความพร้อมของ GPG

เราจะต้องใช้ซอฟต์แวร์ชื่อ `GPG (GNU Privacy Guard)` ในการตรวจสอบความถูกต้องของซอฟต์แวร์ที่เราดาวน์โหลดมา หากไม่มั่นใจว่ามี GPG ติดตั้งอยู่ในคอมพิวเตอร์หรือยัง หรือที่มีอยู่เป็นเวอร์ชั่นอะไร ให้ใช้คำสั่งด้านล่างนี้ในหน้าต่าง terminal เพื่อตรวจสอบ

```bash
gpg --version
```
**ตัวอย่างผลลัพธ์:**

**✅ กรณีที่มี GPG อยู่ในเครื่องแล้ว:**
จะปรากฏข้อมูลเวอร์ชันของซอฟต์แวร์คล้ายกับตัวอย่างนี้:
```text
gpg (GnuPG) 2.4.5
libgcrypt 1.10.3
Copyright (C) 2024 g10 Code GmbH
...
```

**❌ กรณีที่ยังไม่มี GPG:**
จะขึ้นข้อความแจ้งเตือนว่าไม่พบคำสั่ง (Command not found) ดังนี้:
*   **Windows:** `'gpg' is not recognized as an internal or external command, operable program or batch file.`
*   **macOS/Linux:** `bash: gpg: command not found`

> **[ ⚠️ สำคัญ!!! ]**
> หากยังไม่มี GPG และต้องการจะติดตั้งเพื่อใช้งาน ให้อ่านและทำตาม [คู่มือการติดตั้ง GPG](./gpg_installation.md) ก่อนจึงกลับมาทำขั้นตอนต่อไป

--

### 2.2.2 นำเข้า Public Key ของผู้พัฒนา

ผู้พัฒนาได้ประกาศ Fingerprint ของ Public Key ไว้ในหน้า Releases บน Github ว่าคือ `8C8ECD3F660CA53CD878792A6E38A462ED2EF525` ซึ่งเราจะนำเข้า Public Key นี้เข้ามายัง GPG ของเราจากเซิร์ฟเวอร์โดยตรงด้วยคำสั่ง:

```bash
gpg --keyserver hkps://keyserver.ubuntu.com --recv-keys 8C8ECD3F660CA53CD878792A6E38A462ED2EF525
```

เมื่อสำเร็จจะพบกับข้อความประมาณนี้:

```text
gpg: key 6E38A462ED2EF525: public key "Ta Tat Tai (Nunchuk binary release signing key) <tatattai@gmail.com>" imported
gpg: Total number processed: 1
gpg:               imported: 1
```

สามารถตรวจสอบให้แน่ใจว่าได้นำเข้าคีย์ของผู้พัฒนาและมี **Fingerprint** ที่ถูกต้องตรงตามหน้าเว็บทางการด้วยคำสั่ง:

```bash
gpg --list-keys
```

**ผลลัพธ์ที่ถูกต้อง:**
คุณควรจะเห็นชื่อ **Ta Tat Tai (Nunchuk binary release signing key)** และ Fingerprint ที่ระบุในบรรทัดถัดมาคือ `8C8ECD3F660CA53CD878792A6E38A462ED2EF525`:

```text
...
pub   rsa4096 2020-11-04 [SC]
      8C8ECD3F660CA53CD878792A6E38A462ED2EF525
uid           [ unknown] Ta Tat Tai (Nunchuk binary release signing key) <tatattai@gmail.com>
sub   rsa4096 2020-11-04 [E]
      F48B960A207E7969CFC8D0781C5EB1932D875D3E
...
```

--

### 2.2.3 ตรวจสอบลายเซ็นของรายการค่า Hash

ใช้คำสั่ง `cd` เข้าไปยังโฟลเดอร์ที่เก็บไฟล์ทั้ง 2 รายการไว้ จากนั้นรันคำสั่งเพื่อตรวจสอบว่าเนื้อหาใน `SHA256SUMS.asc` ถูกเขียนโดย Nunchuk จริงหรือไม่:

```bash
gpg --verify SHA256SUMS.asc
```

**ผลลัพธ์:** ต้องขึ้นคำว่า **"Good signature from Ta Tat Tai"** เช่น

**ตัวอย่างผลลัพธ์ที่ถูกต้อง:**
```text
gpg: Signature made 12/08/25 22:26:00 SE Asia Standard Time
gpg:                using RSA key 8C8ECD3F660CA53CD878792A6E38A462ED2EF525
gpg: Good signature from "Ta Tat Tai (Nunchuk binary release signing key) <tatattai@gmail.com>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
      8C8ECD3F660CA53CD878792A6E38A462ED2EF525
gpg: WARNING: not a detached signature; file 'SHA256SUMS' was NOT verified!
```

--

### 2.2.4 ตรวจสอบค่า Hash ของไฟล์ติดตั้ง

ด้านในไฟล์ `SHA256SUMS.asc` Ta Tat Tai ได้ระบุค่า Hash ของไฟล์ .zip ทุกไฟล์ในเวอร์ชั่น 2.4.0 เอาไว้ หากเรา Hash ไฟล์ติดตั้งแล้วได้ค่า Hash ตรงกับที่ระบุในไฟล์ `SHA256SUMS.asc` แสดงว่าไฟล์ปลอดภัย 100%

1. คำสั่งที่ใช้ hash ไฟล์ .zip
*   **Windows:**
```bash
CertUtil -hashfile nunchuk-window-v2.4.0.zip SHA256
```
*   **macOS:**
```bash
sha256sum nunchuk-macos-v2.4.0.zip
```
*   **Linux:**
```bash
sha256sum nunchuk-linux-v2.4.0.zip
```

2. คำสั่งที่ใช้เปิดไฟล์ `SHA256SUMS.asc`
*   **Windows:**
```bash
type SHA256SUMS.asc
```
*   **macOS/Linux:**
```bash
cat SHA256SUMS.asc
```

เปรียบเทียบตัวเลขที่ได้กับตัวเลขในไฟล์ `SHA256SUMS.asc` หากตรงกันแสดงว่าไฟล์ที่เราดาวน์โหลดมานี้เป็นของแท้ที่ส่งตรงจากนักพัฒนาถึงมือเราโดยที่ไม่มีการถูกแก้ไขเปลี่ยนแปลงใดๆ

---

# 3. การติดตั้ง
*   **Windows:** รันไฟล์ `.exe` และทำตามขั้นตอนที่ปรากฏ
*   **macOS:** เปิดไฟล์ `.dmg` แล้วลาก Nunchuk เข้าไปยังโฟลเดอร์ Applications

---
เพียงเท่านี้ คุณก็สามารถเริ่มต้นใช้งาน Nunchuk Wallet ได้อย่างมั่นใจแล้ว
