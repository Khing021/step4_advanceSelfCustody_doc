# การติดตั้ง GPG (GNU Privacy Guard)

หากคุณรันคำสั่ง `gpg --version` แล้วพบข้อความว่า `Command not found` หรือระบบไม่รู้จักคำสั่ง แสดงว่าเครื่องของคุณยังไม่มี GPG ติดตั้งอยู่ โปรดทำตามขั้นตอนด้านล่างตามระบบปฏิบัติการที่คุณใช้งาน

## 1. Windows
สำหรับ Windows เราแนะนำให้ใช้ **Gpg4win** ซึ่งเป็นชุดเครื่องมือมาตรฐาน

1. ไปที่เว็บไซต์ [gpg4win.org](https://gpg4win.org/)
2. คลิกปุ่ม **Download** (คุณสามารถเลือกบริจาค หรือใส่ $0 เพื่อดาวน์โหลดฟรีได้)
3. รันไฟล์ตัวติดตั้ง `.exe` ที่ดาวน์โหลดมา
4. ในขั้นตอนเลือก Component ให้แน่ใจว่าเลือก **GnuPG** (ส่วน Cleopatra เป็น GUI สำหรับจัดการ Key ซึ่งจะติดตั้งหรือไม่ก็ได้)
5. เมื่อติดตั้งเสร็จ ให้ลองรันคำสั่งนี้ใน Terminal (PowerShell หรือ Command Prompt)เพื่อตรวจสอบ:

```bash
gpg --version
```

หากติดตั้งสำเร็จจะปรากฏข้อมูลเวอร์ชันของซอฟต์แวร์คล้ายกับตัวอย่างนี้:

```text
gpg (GnuPG) 2.4.5
libgcrypt 1.10.3
Copyright (C) 2024 g10 Code GmbH
...
```


## 2. macOS
มี 2 วิธีที่แนะนำ:

### วิธีที่ A: ใช้ Homebrew (แนะนำสำหรับสาย Developer)
หากคุณมี Homebrew ติดตั้งอยู่แล้ว ให้รันคำสั่ง:
```bash
brew install gnupg
```

### วิธีที่ B: ใช้ GPG Suite
1. ไปที่ [gpgtools.org](https://gpgtools.org/)
2. ดาวน์โหลด **GPG Suite**
3. ติดตั้งตามขั้นตอนปกติบน macOS

เมื่อติดตั้งเสร็จ ให้ลองรันคำสั่งนี้ใน Terminal (PowerShell หรือ Command Prompt)เพื่อตรวจสอบ:

```bash
gpg --version
```

หากติดตั้งสำเร็จจะปรากฏข้อมูลเวอร์ชันของซอฟต์แวร์คล้ายกับตัวอย่างนี้:

```text
gpg (GnuPG) 2.4.5
libgcrypt 1.10.3
Copyright (C) 2024 g10 Code GmbH
...
```


## 3. Linux
สำหรับ Linux ส่วนใหญ่มักจะมี GPG ติดตั้งมาให้แล้ว หากไม่มีสามารถติดตั้งได้ผ่าน Package Manager:

- **Debian / Ubuntu / Kali:**
  ```bash
  sudo apt update
  sudo apt install gnupg
  ```

- **Fedora:**
  ```bash
  sudo dnf install gnupg2
  ```

- **Arch Linux:**
  ```bash
  sudo pacman -S gnupg
  ```

เมื่อติดตั้งเสร็จ ให้ลองรันคำสั่งนี้ใน Terminal (PowerShell หรือ Command Prompt)เพื่อตรวจสอบ:

```bash
gpg --version
```

หากติดตั้งสำเร็จจะปรากฏข้อมูลเวอร์ชันของซอฟต์แวร์คล้ายกับตัวอย่างนี้:

```text
gpg (GnuPG) 2.4.5
libgcrypt 1.10.3
Copyright (C) 2024 g10 Code GmbH
...
```

---

เมื่อติดตั้งเสร็จแล้ว ให้กลับไปดำเนินการต่อในส่วนที่ค้างอยู่

- กลับไปที่ Sparrow Wallet: [2.2.2 นำเข้า Public Key ของผู้พัฒนา](./sparrow_installation.md#222-นำเข้า-public-key-ของ-craig-raw-ผู้พัฒนา)

