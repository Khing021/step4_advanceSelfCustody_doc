# การติดตั้งและใช้งาน Wasabi Wallet

# 1. เกี่ยวกับ Wasabi Wallet
**Wasabi Wallet** เป็น Bitcoin Wallet บน Desktop ที่สร้างขึ้นโดยเน้นเรื่องความเป็นส่วนตัว (Privacy) เป็นอันดับหนึ่ง โดยมีจุดเด่นคือระบบ **CoinJoin** ที่ช่วยตัดความเชื่อมโยงของเหรียญได้อย่างมีประสิทธิภาพ ถือเป็นเครื่องมือสำคัญสำหรับผู้ที่ต้องการรักษาความลับทางการเงินในระดับสูง มีฟีเจอร์เด่นดังนี้:

*   **Default Privacy:** มีระบบรักษาความเป็นส่วนตัวที่แข็งแกร่งตั้งแต่เริ่มต้น เช่น การเชื่อมต่อผ่าน Tor โดยอัตโนมัติ
*   **WabiSabi:** โปรโตคอลสำหรับการทำ CoinJoin เพื่อเพิ่มความเป็นส่วนตัวให้กับ UTXO
*   **Client-Side Filtering:** ตรวจสอบยอดเงินโดยไม่ต้องแจ้ง Public Key ให้ Server ทราบ (เทคนิค Neutrino-like)
*   **Broad Hardware Support:** รองรับ Hardware Wallet ชั้นนำ (Coldcard, Ledger, Trezor) และมี Interface ที่ใช้งานง่าย

> **[ ⚠️ สำคัญ!!! ]** Wasabi Wallet เป็นซอฟต์แวร์ที่ทำงานบนคอมพิวเตอร์เท่านั้น ไม่มี Wasabi Wallet ที่สามารถใช้งานได้ผ่าน web browser หรือ smartphone/tablet หากพบเห็นคือซอฟต์แวร์หลอกลวง (Scam) ทั้งสิ้น

> ช่องทางประชาสัมพันธ์อย่างเป็นทางการของ Wasabi Wallet
> * Website: [wasabiwallet.io](https://wasabiwallet.io/)
> * Tor: http://wasabiukrxmkdgve5kynjztuovbg43uxcbcxn6y2okcrsg7gb6jdmbad.onion/
> * Github: [WalletWasabi](https://github.com/WalletWasabi/WalletWasabi)
> * X: [Wasabi Wallet](https://x.com/wasabiwallet)
> * Nostr: [npub1jw7scmeuewhywwytqxkxec9jcqf3znw2fsyddcn3948lw9q950ps9y35fg](https://njump.me/npub1jw7scmeuewhywwytqxkxec9jcqf3znw2fsyddcn3948lw9q950ps9y35fg)

ปัจจุบันที่เขียนคู่มือนี้ (เมษายน 2026) Wasabi Wallet เวอร์ชั่นล่าสุดคือ `2.7.2`

# 2. การดาวน์โหลดและตรวจสอบ

เพื่อให้มั่นใจว่าซอฟต์แวร์ที่ดาวน์โหลดมานั้นเป็นซอฟต์แวร์ของแท้จากนักพัฒนาตัวจริง และไม่ถูกดัดแปลงแก้ไขโดยผู้ประสงค์ร้าย เราจำเป็นต้องดาวน์โหลดจากแหล่งที่มาทางการ และตรวจสอบความถูกต้องของซอฟต์แวร์ก่อนการติดตั้ง

ลิงก์ดาวน์โหลดอย่างเป็นทางการ ขั้นตอนการตรวจสอบความถูกต้องของซอฟต์แวร์ และการติดตั้งจากเว็บไซต์ทางการ (ภาษาอังกฤษ) สามารถดูได้ที่ [docs.wasabiwallet.io/using-wasabi/InstallPackage.html](https://docs.wasabiwallet.io/using-wasabi/InstallPackage.html) หรือจะทำตามขั้นตอนด้านล่างนี้ก็ได้เช่นกัน (ภาษาไทย)

## 2.1 ดาวน์โหลดไฟล์ที่จำเป็น

ดาวน์โหลดไฟล์ติดตั้งและไฟล์ลายเซ็นดิจิทัลจากหน้าดาวน์โหลดทางการเท่านั้น:
*   **Website:** [wasabiwallet.io/#download](https://wasabiwallet.io/#download)
*   **Tor:** [wasabiukrxmkdgve5kynjztuovbg43uxcbcxn6y2okcrsg7gb6jdmbad.onion/#download](http://wasabiukrxmkdgve5kynjztuovbg43uxcbcxn6y2okcrsg7gb6jdmbad.onion/#download)
*   **Github:** [WalletWasabi/WalletWasabi/releases](https://github.com/WalletWasabi/WalletWasabi/releases)

ควรสร้างโฟลเดอร์ใหม่แยกต่างหากและดาวน์โหลดไฟล์ทั้ง 2 รายการนี้มาไว้ในโฟลเดอร์เดียวกัน:
1.  **ไฟล์ติดตั้ง (Installer):** ตาม OS ของคุณ (เช่น `.msi`, `.dmg`, `.deb` หรือ `.tar.gz`)
2.  **Signature file:** ไฟล์ที่มีนามสกุลต่อท้ายด้วย `.asc` (เช่น `Wasabi-2.7.2.msi.asc`)

## 2.2 ตรวจสอบความถูกต้อง

### 2.2.1 เช็คความพร้อมของ GPG

เราจะต้องใช้ซอฟต์แวร์ชื่อ `GPG (GNU Privacy Guard)` ในการตรวจสอบความถูกต้องของซอฟต์แวร์ที่เราดาวน์โหลดมา หากไม่มั่นใจว่ามี GPG ติดตั้งอยู่ในคอมพิวเตอร์หรือยัง ให้ใช้คำสั่งด้านล่างนี้ในหน้าต่าง terminal เพื่อตรวจสอบ:

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

### 2.2.2 นำเข้า Public Key ของ zkSNACKs (ผู้พัฒนา)

1. ดาวน์โหลดคีย์ของ zkSNACK (ทีมพัฒนา) โดยการเข้าไปที่ [github.com/WalletWasabi/WalletWasabi/blob/master/PGP.txt](https://github.com/WalletWasabi/WalletWasabi/blob/master/PGP.txt) แล้วกดปุ่ม `Download raw file` บริเวณด้านขวาของหน้าเว็บเพื่อดาวน์โหลดไฟล์ `PGP.txt` ลงมาในคอมพิวเตอร์ของเรา
2. เปิดหน้าต่าง terminal แล้วใช้คำสั่ง `cd` เข้าไปยังโฟลเดอร์ที่เก็บไฟล์ `PGP.txt` ไว้ จากนั้นรันคำสั่งนี้เพื่อนำเข้าคีย์ของ zkSNACK มาไว้ใน GPG:

```bash
gpg --import PGP.txt
```

เมื่อสำเร็จจะพบกับข้อความประมาณนี้:

```text
gpg: key 856348328949861E: 5 signatures not checked due to missing keys
gpg: key 856348328949861E: public key "zkSNACKs <zksnacks@gmail.com>" imported
gpg: Total number processed: 1
gpg:               imported: 1
gpg: no ultimately trusted keys found
```

สามารถตรวจสอบให้แน่ใจว่าได้นำเข้าคีย์ของผู้พัฒนาและมี **Fingerprint** ที่ถูกต้องตรงตามหน้าเว็บทางการด้วยคำสั่ง:

```bash
gpg --list-keys
```

**ผลลัพธ์ที่ถูกต้อง:**
คุณควรจะเห็นชื่อ **zkSNACKs** และ Fingerprint ที่ระบุในบรรทัดถัดมาต้องตรงกับที่แจ้งไว้ในเว็บไซต์ทางการคือ `6FB3 872B 5D42 292F 5992 0797 8563 4832 8949 861E`:

```text
pub   rsa2048 2019-08-22 [SC] [expires: 2028-02-24]
      6FB3872B5D42292F59920797856348328949861E
uid           [ unknown] zkSNACKs <zksnacks@gmail.com>
```

--

### 2.2.3 ตรวจสอบลายเซ็นของไฟล์ติดตั้ง

ใช้คำสั่ง `cd` เข้าไปยังโฟลเดอร์ที่เก็บไฟล์ติดตั้งและไฟล์ `.asc` ไว้ จากนั้นรันคำสั่งตรวจสอบ:

```bash
# ตัวอย่างสำหรับ Windows (หากใช้ไฟล์เวอร์ชัน 2.7.2)
gpg --verify Wasabi-2.7.2.msi.asc Wasabi-2.7.2.msi
```

**ผลลัพธ์:** ต้องขึ้นคำว่า **"Good signature from zkSNACKs"** เช่น:

```text
gpg: Signature made 11/17/25 07:33:11 SE Asia Standard Time
gpg:                using RSA key 6FB3872B5D42292F59920797856348328949861E
gpg: Good signature from "zkSNACKs <zksnacks@gmail.com>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
```

ตอนนี้เรามั่นใจได้แล้วว่าไฟล์ติดตั้งที่เราดาวน์โหลดมานั้นเป็นของแท้ที่ส่งตรงจากผู้พัฒนา zkSNACKs ถึงมือเราโดยที่ไม่มีการถูกแก้ไขเปลี่ยนแปลงใดๆ


# 3. การติดตั้ง

เมื่อแน่ใจว่าไฟล์ถูกต้องแล้ว ให้เริ่มการติดตั้งตามระบบปฏิบัติการของคุณ:

*   **Windows:** รันไฟล์ `.msi` และทำตามขั้นตอนที่ปรากฏ
*   **macOS:** เปิดไฟล์ `.dmg` แล้วลาก Wasabi เข้าไปยังโฟลเดอร์ Applications
*   **Linux:** แตกไฟล์ `.tar.gz` และรันตัวโปรแกรม หรือใช้ `dpkg` สำหรับไฟล์ที่รองรับ

> เมื่อติดตั้งสำเร็จแล้ว คุณสามารถลบไฟล์ที่เกี่ยวข้องทั้งหมดได้


# 4. การสร้างวอลเล็ต

หลังจากเพิ่งติดตั้ง Wasabi Wallet และเปิดใช้งานครั้งแรก Wasabi จะใช้เวลานานในการซิงค์ข้อมูลบล็อกเชนที่จำเป็น นี่คือสาเหตุที่เราจึงทำคู่มือนี้ขึ้นมาเพื่อให้ทุกคนติดตั้ง Wasabi Wallet ในคอมพิวเตอร์ของตัวเองและซิงค์ข้อมูลให้พร้อมเรียนมาจากบ้านเพื่อความสะดวกรวดเร็วในการเรียนการสอน

> **[ ⚠️ สำคัญ!!! ]** ขณะที่สาธิตในห้องเรียน คุณสามารถทำตามได้โดยใช้บิตคอยน์จริง หากต้องการทำเช่นนั้น หรือมีความเป็นไปได้ที่จะทำเช่นนั้น ให้สร้าง wallet อย่างรัดกุมปลอดภัย เพราะเราจะใช้บิตคอยน์จริงในการทำธุรกรรม

1.  กด `Get Started` เพื่อเริ่มต้นสร้างวอลเล็ตใหม่
![หน้าต่างต้อนรับ](https://github.com/Khing021/step4_advanceSelfCustody_doc/blob/main/attachment/img/wasabi01-firstScreen.png)
2.  เลือก `Create a new wallet`
3.  ตั้งชื่อวอลเล็ตตามชอบ
4.  เลือกรูปแบบของ Backup
    *   หากต้องการสร้าง seed phrase 12 คำ 1 ชุด (BIP39) ให้เลือก `Recovery words backup`
    *   หากต้องการสร้าง seed phrase 20 คำ หลายชุด (shares: n) ซึ่งสามารถกู้คืนเงินได้ด้วยการใช้เพียงบางชุด (threshold: m) ให้เลือก `Multi-share backup`
5.  จด **Recovery Words** (Seed Phrase) อย่างระมัดระวังและเป็นส่วนตัว แนะนำให้ทำสำเนาชุดหนึ่งไว้ที่บ้าน และอีกชุดหนึ่งให้พกติดตัวมาเรียนด้วย (แต่ไม่ต้องนำออกมาโชว์หากไม่มีเหตุจำเป็น)
6.  ในหน้าถัดมา ทบทวนความถูกต้องของ **Recovery Words** โดยการเรียงลำดับคำให้ถูกต้อง
7.  ตั้ง **Passphrase** สำหรับใช้งานวอลเล็ต
    *   หากไม่ต้องการใช้งาน Passphrase สามารถปล่อยให้ช่องกรอก Passphrase ว่างไว้แล้วกด `Continue` ได้เลย
    *   แต่หากต้องการใช้งาน Passphrase ทุกครั้งที่ใช้งานวอลเล็ต รวมไปถึงหากเราต้องการนำ **Recovery Words** ไปใช้กู้คืนวอลเล็ตในเครื่องอื่น เราจะต้องกรอก **Passphrase** นี้ให้ถูกต้องด้วยเช่นเดียวกัน หากกรอกไม่ถูกต้อง จะไม่สามารถเข้าถึงเงินได้อีกเลย
8.  เมื่อสร้างวอลเล็ตเสร็จแล้ว Wasabi จะเข้าสู่หน้าจอการซิงค์ข้อมูล ให้เปิดคอมพิวเตอร์ทิ้งไว้ (หากจำเป็นต้องปิดซอฟต์แวร์กลางคันสามารถปิดซอฟต์แวร์แล้วเปิดมาซิงค์ต่อภายหลังได้)
![วอลเล็ตกำลังซิงก์](https://github.com/Khing021/step4_advanceSelfCustody_doc/blob/main/attachment/img/wasabi02-syncing.png)
9.  เมื่อซิงค์ข้อมูลเสร็จแล้ววอลเล็ตของคุณจะพร้อมใช้งาน
![วอลเล็ตพร้อมใช้งาน](https://github.com/Khing021/step4_advanceSelfCustody_doc/blob/main/attachment/img/wasabi03-walletReady.png)

---

เพียงเท่านี้ คุณก็สามารถเริ่มต้นใช้งาน Wasabi Wallet ได้อย่างมั่นใจแล้ว
