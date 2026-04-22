# Multisig

## 0. เปลี่ยนเป็น Testnet

เพื่อความสบายใจในกิจกรรมนี้เราจะใช้งาน Bitcoin Testnet แทนที่จะเป็นบิตคอยน์จริง

เมื่อเปิด Sparrow Wallet ขึ้นมาแล้วให้ไปที่เมนู `Tools` > `Restart In` > `Testnet4`

## 1. รวบรวม keystore

เพื่อให้ส่งข้อมูล keystore ไปให้เพื่อนได้สะดวกและเป็นระเบียบ เราได้สร้าง Google Form เพื่อรับข้อมูล keystore จากทุกคนมาไว้รวมกันในที่เดียว

เมื่อทุกคนดึง keystore ของตัวเองด้วย Sparrow Wallet แล้ว ให้กรอกข้อมูลลงใน [Google Form นี้](https://forms.gle/zBBEp5fCn2zoKXJq7)

- **Label:** ตั้งชื่อเป็นชื่อเล่นหรือนามแฝงของตัวเอง และอาจเพิ่มตัวเลขลำดับไว้ข้างหลังเผื่อส่งผิดแล้วต้องการส่งใหม่จะได้ไม่สับสน เช่น `khing01`
- **Master fingerprint:** จะนำมากรอกก็ได้ หรือถ้าเราไม่ได้คิดจะเอา hardware wallet ไปเสียบใช้งานเครื่องของเพื่อนให้กรอกไปเป็น `00000000` (8 หลัก)
- **Derivation Path:** ให้นำข้อมูลจากช่อง `Derivation:` มากรอก
- **tpub:** ให้นำข้อมูลจากช่อง `tpub / Vpub:` (หากทำใน Mainnet ช่องนี้จะเป็น `xpub / Zpub:`) มากรอก โดยดูให้แน่ใจว่าเป็น tpub คือขึ้นต้นด้วย `tpub...` หากที่แสดงอยู่เป็น `Vpub...` ให้เปลี่ยนกลับมาด้วยการกดปุ่มรูปลูกศร (`Show as tpub`) ที่ด้านขวาของช่อง

## 2. สร้าง multisig wallet

ทุกคนสามารถสร้าง multisig wallet ให้สมบูรณ์ได้ด้วยด้วยการนำข้อมูล keystore ของเพื่อนมากรอกใน Sparrow Wallet ของตัวเอง โดยการเลือกเพิ่ม keystore ให้กับกระเป๋า Multisig ด้วยวิธี `xPub / Watch Only Wallet` 

- กรณีกลุ่ม 2 คน สร้างกระเป๋าแบบ 2-of-3 โดยใช้ keystore ของตัวเอง 1 อัน ของเพื่อน 1 อัน และของครูอีก 1 อัน
- กรณีกลุ่ม 3 คน สร้างกระเป๋า Multisig แบบ 3-of-4 โดยใช้ keystore ของตัวเอง 1 อัน ของเพื่อน 2 อัน และของครูอีก 1 อัน

ทุกคนสามารถเข้าไปดูข้อมูล keystore ที่เพื่อน ๆ ส่งเข้ามาใน Google Form ในขั้นตอนที่แล้วได้ที่ [Google Sheet นี้](https://docs.google.com/spreadsheets/d/1TigR3eR-2tZgTySorxq--4zAobFnWp94kuvkAWLzgRc/edit?resourcekey=&gid=142427351#gid=142427351)

## 3. ส่งการบ้าน

ให้ทุกคนนำ Wallet Descriptor ที่สร้างได้ และข้อมูลอื่น ๆ ที่ได้จากการสร้าง Multisig Wallet มาส่งใน [Google Form นี้](https://forms.gle/afWEZKXykJNmFw4b7)

- **Label #1, Label #2, Label #3, Label #4:** ระบุชื่อ keystore ที่ใช้ ควรใช้ชื่อเดียวกับแต่ละคนใช้ตอนส่ง keystore ของตัวเองเข้ามา
- **Wallet Descriptor:** ให้คัดลอก string ยาว ๆ ที่แสดงเมื่อกดปุ่ม `Edit...` ท้ายช่อง `Descriptor:` มากรอก
- **First Address:** ให้นำ address ลำดับแรกของชุด `Receive Addresses` ที่สร้างได้มากรอก (`../0/0`) (address ประเภท Native Segwit ใน Testnet จะขึ้นต้นด้วย `tb1q...`)

## 4. ตรวจการบ้านเพื่อน

ดูข้อมูลที่เพื่อนส่งเข้ามาผ่าน Google Form ในขั้นตอนที่แล้วได้ที่ [Google Sheet นี้](https://docs.google.com/spreadsheets/d/1TigR3eR-2tZgTySorxq--4zAobFnWp94kuvkAWLzgRc/edit?resourcekey=&gid=1713847442#gid=1713847442)

ลองสร้างกระเป๋าใหม่ใน Sparrow Wallet แล้วกรอก Wallet Descriptor ที่เพื่อนทำได้เข้าไปแล้วเช็คว่าได้ address ตรงกันหรือไม่

## 5. ครูส่งเงินให้

ครูจะส่งเงินจำนวนหนึ่งเข้าไปในกระเป๋า Multisig ของแต่ละกลุ่มโดยอ้างอิงจาก address ที่ส่งมา

## 6. ส่งเงินคืนให้ครู

ให้ทุกกลุ่มส่งเงินคืนให้ครู โดยใช้ address ของครูที่ให้ไว้

1. สมาชิกคนหนึ่งในกลุ่มเป็นคนที่สร้าง transaction เซ็นธุรกรรมในส่วนของตัวเอง เซฟไฟล์ออกมา แล้วส่งให้เพื่อนคนที่ 2
2. สมาชิกคนที่สอง (กรณีกลุ่ม 3 คน) เปิดไฟล์ transaction ขึ้นมาใน Sparrow Wallet ของตัวเอง เซ็นธุรกรรมในส่วนของตัวเอง เซฟไฟล์ออกมา แล้วส่งให้เพื่อนคนที่ 3
3. สมาชิกคนสุดท้ายเปิดไฟล์ transaction ขึ้นมาใน Sparrow Wallet ของตัวเอง เซ็นธุรกรรมในส่วนของตัวเอง แล้ว Broadcast ธุรกรรมออกไปในเครือข่าย Blockchain

> การส่งข้อมูลธุรกรรมระหว่างกันสามารถทำได้สองวิธีหลัก ๆ หนึ่งคือการเซฟเป็นไฟล์ .psbt ออกมาแล้วส่งให้กัน หรืออีกวิธีคือการเปลี่ยนข้อมูลธุรกรรมเป็น QR code แล้วสแกนด้วยกล้องของอีกฝ่าย ในกรณีที่ต้องการส่งเป็นไฟล์แล้วไม่มีช่องทางส่วนตัวที่สะดวกในการส่งไฟล์ สามารถใช้วิธีอัพโหลดไฟล์เข้ามาได้ใน [Google Drive นี้](https://drive.google.com/drive/folders/1PGt_vrztzN_F0v4zYUsDzp3Bo6R8M0HB?usp=sharing)