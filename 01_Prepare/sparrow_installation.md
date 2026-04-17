# การติดตั้งและใช้งาน Sparrow Wallet

# 1. เกี่ยวกับ Sparrow Wallet
**Sparrow Wallet** เป็นวอลเล็ตบน Desktop ที่เน้นความโปร่งใสและการควบคุมทุกอย่างได้ด้วยตัวเอง (Full Control) ถือเป็นเครื่องมือระดับ "Swiss Army Knife" สำหรับผู้ใช้งาน Bitcoin ขั้นสูง โดยมีฟีเจอร์เด่นที่สำคัญคือ:

*   **UTXO Management:** สามารถเลือกเหรียญ (Coin Selection) และจัดการ UTXO ได้อย่างละเอียด พร้อมระบบการติดป้ายกำกับ (Labeling) ที่ยอดเยี่ยม
*   **Privacy & Node Connectivity:** เชื่อมต่อกับ Bitcoin Node ของตัวเองได้โดยตรง (ทั้ง Bitcoin Core และ Electrum) รองรับ Tor ในตัวเพื่อรักษาความเป็นส่วนตัว
*   **Broad Hardware Support:** รองรับการเชื่อมต่อกับ Hardware Wallet แถบทุกแบรนด์ชั้นนำ (Coldcard, BitBox02, Jade, Ledger, Trezor)
*   **Advanced Tools:** รองรับการทำ Multi-sig, PayJoin, Silent Payments, และมีหน้าจอ Transaction Editor ที่ช่วยให้เห็นโครงสร้างของธุรกรรมอย่างละเอียดก่อนกดยืนยัน

นอกเหนือจาก wallet software ที่พัฒนาโดยผู้ผลิต hardware wallet รุ่นที่คุณใช้แล้ว ผมมักจะแนะนำให้ผู้ใช้งานบิตคอยน์ทุกคนติดตั้ง Sparrow Wallet ไว้ในคอมพิวเตอร์ของตัวเองเป็นซอฟต์แวร์สำรองเสมอ

> **[ ⚠️ สำคัญ!!! ]** Sparrow Wallet เป็นซอฟต์แวร์/แอปพลิเคชันที่ทำงานบนคอมพิวเตอร์เท่านั้น ไม่มี Sparrow Wallet ที่สามารถใช้งานได้ผ่าน web browser หรือ smartphone/tablet พวกนั้นล้วนเป็นซอฟต์แวร์หลอกลวงทั้งสิ้น

> ช่องทางประชาสัมพันธ์อย่างเป็นทางการของ Sparrow Wallet
> * Website: [sparrowwallet.com](https://sparrowwallet.com/)
> * Github: [sparrowwallet/sparrow](https://github.com/sparrowwallet/sparrow)
> * X: [SparrowWallet](https://x.com/SparrowWallet)
> * Telegram: [Sparrow Wallet](https://t.me/sparrowwallet)

ปัจจุบันที่เขียนคู่มือนี้ (เมษายน 2026) Sparrow Wallet เวอร์ชั่นล่าสุดคือ `2.4.2` เราจะสาธิตการดาวน์โหลดและตรวจสอบไฟล์เวอร์ชั่นนี้ หากต้องการดาวน์โหลดและติดตั้งเวอร์ชั่นอื่นให้เปลี่ยนชื่อไฟล์ในแต่ละคำสั่งเป็นไฟล์เวอร์ชั่นที่คุณต้องการ

# 2. การดาวน์โหลดและตรวจสอบ

เพื่อให้มั่นใจว่าซอฟต์แวร์ที่ดาวน์โหลดมานั้นเป็นซอฟต์แวร์ของแท้จากนักพัฒนาตัวจริง และไม่ถูกดัดแปลงแก้ไขโดยผู้ประสงค์ร้าย เราจำเป็นต้องดาวน์โหลดจากแหล่งที่มาทางการ และตรวจสอบความถูกต้องของซอฟต์แวร์ก่อนการติดตั้ง

ลิงก์ดาวน์โหลดอย่างเป็นทางการ ขั้นตอนการตรวจสอบความถูกต้องของซอฟต์แวร์ และการติดตั้งจากเว็บไซต์ทางการ (ภาษาอังกฤษ) สามารถดูได้ที่ [sparrowwallet.com/download](https://sparrowwallet.com/download/) หรือจะทำตามขั้นตอนด้านล่างนี้ก็ได้เช่นกัน (ภาษาไทย)

## 2.1 ดาวน์โหลดไฟล์ที่จำเป็น

ดาวน์โหลด Sparrow Wallet จากแหล่งที่มาทางการเท่านั้น:
*   **Website:** [sparrowwallet.com/download](https://sparrowwallet.com/download/)
*   **Github:** [sparrowwallet/sparrow/releases](https://github.com/sparrowwallet/sparrow/releases)

เพื่อความสะดวกในการตรวจสอบความถูกต้องของซอฟต์แวร์ ควรสร้างโฟลเดอร์ใหม่แยกต่างหากและดาวน์โหลดไฟล์ทั้ง 3 รายการนี้มาไว้ในโฟลเดอร์เดียวกัน:
1.  **ไฟล์ติดตั้ง (Installer):** ตาม OS ของคุณ (.exe, .dmg, .deb หรือ .tar.gz)
2.  **Manifest file:** ไฟล์ชื่อ `sparrow-2.4.2-manifest.txt` เป็นไฟล์รายการค่า hash ของไฟล์ติดตั้งทุกตัวในเวอร์ชั่นนี้
3.  **Manifest Signature:** ไฟล์ชื่อ `sparrow-2.4.2-manifest.txt.asc` เป็นลายเซ็นดิจิทัลซึ่งผู้พัฒนาได้ใช้ private key ของตนเองเซ็นไว้เพื่อรับรองความถูกต้องให้กับไฟล์ manifest



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

### 2.2.2 นำเข้า Public Key ของ Craig Raw (ผู้พัฒนา)

นำเข้าคีย์ของผู้พัฒนา Sparrow Wallet มาไว้ใน gpg ของคอมพิวเตอร์เราด้วยคำสั่ง

   ```bash
   curl https://keybase.io/craigraw/pgp_keys.asc | gpg --import
   ```

เมื่อสำเร็จจะพบกับข้อความประมาณนี้:

```text
...
gpg: key E94618334C674B40: public key "Craig Raw <craig@sparrowwallet.com>" imported
gpg: Total number processed: 1
gpg:               imported: 1
```

สามารถตรวจสอบให้แน่ใจว่าได้นำเข้าคีย์ของผู้พัฒนาแล้วด้วยคำสั่ง:

```bash
gpg --list-keys
```

ซึ่งเราควรจะพบชื่อ **Craig Raw** ปรากฏอยู่ในรายการ

```text
...
pub   rsa4096 2019-10-03 [SC] [expires: 2027-09-18]
      D4D0D3202FC06849A257B38DE94618334C674B40
uid           [ unknown] Craig Raw <craig@sparrowwallet.com>
sub   rsa4096 2019-10-03 [E] [expires: 2027-09-18]
      33AA403D5060DC80EBC4E68B3FB2D3544ECAF6DA
...
```

--

### 2.2.3 ตรวจสอบลายเซ็นไฟล์ Manifest

ใช้คำสั่ง `cd` เข้าไปยังโฟลเดอร์ที่เก็บไฟล์ทั้ง 3 รายการนี้ไว้ จากนั้นเราจะใช้ประโยชน์จากไฟล์ `sparrow-2.4.2-manifest.txt.asc` เพื่อตรวจสอบว่าเนื้อหาใน `sparrow-2.4.2-manifest.txt` ถูกเขียนโดย Craig Raw จริงหรือไม่:

```bash
gpg --verify sparrow-2.4.2-manifest.txt.asc
```
**ผลลัพธ์:** ต้องขึ้นคำว่า **"Good signature from Craig Raw"** เช่น

```text
gpg: assuming signed data in 'sparrow-2.4.2-manifest.txt'
gpg: Signature made 06/09/25 21:20:46 SE Asia Standard Time
gpg:                using RSA key D4D0D3202FC06849A257B38DE94618334C674B40
gpg: Good signature from "Craig Raw <craig@sparrowwallet.com>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
      D4D0D3202FC06849A257B38DE94618334C674B40
```

ตอนนี้เรามั่นใจได้แล้วว่า Craig Raw ได้รับรองความถูกต้องของไฟล์ `sparrow-2.4.2-manifest.txt` และที่เราดาวน์โหลดมานั้นเป็นไฟล์ที่ถูกต้อง

--

### 2.2.4 ตรวจสอบ Hash ของไฟล์ติดตั้ง

ด้านในไฟล์ `sparrow-2.4.2-manifest.txt` Craig Raw ได้ระบุค่า Hash ของไฟล์ติดตั้งทุกไฟล์ในเวอร์ชั่น 2.4.2 เอาไว้ หากเรา Hash ไฟล์ติดตั้งแล้วได้ค่า Hash ตรงกับที่ระบุในไฟล์ menifest แสดงว่าไฟล์ปลอดภัย 100%

1. คำสั่งที่ใช้ hash ไฟล์ติดตั้ง
*   **Windows:**
```bash
CertUtil -hashfile <ชื่อไฟล์ติดตั้ง> SHA256
```
*   **macOS/Linux:**
```bash
sha256sum <ชื่อไฟล์ติดตั้ง>
```

2. คำสั่งที่ใช้เปิดไฟล์ manifest.txt
*   **Windows:**
```bash
type sparrow-2.4.2-manifest.txt
```
*   **macOS/Linux:**
```bash
cat sparrow-2.4.2-manifest.txt
```

เปรียบเทียบตัวเลขที่ได้กับตัวเลขในไฟล์ menifest หากตรงกันแสดงว่าไฟล์ที่เราดาวน์โหลดมานี้เป็นของแท้ที่ส่งตรงจากนักพัฒนาถึงมือเราโดยที่ไม่มีการถูกแก้ไขเปลี่ยนแปลงใดๆ

## 3. การติดตั้ง

*   **Windows:** รันไฟล์ `.exe`
*   **macOS:** ลากเข้า Applications
*   **Linux:** แตกไฟล์และรันตัวโปรแกรม หรือใช้ `dpkg` สำหรับไฟล์ `.deb`

> เมื่อติดตั้งสำเร็จแล้ว คุณสามารถลบไฟล์ที่เกี่ยวข้องทั้งหมดได้

---

เพียงเท่านี้ คุณก็สามารถเริ่มต้นใช้งาน Sparrow Wallet ได้อย่างมั่นใจแล้ว
