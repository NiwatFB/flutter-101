# 🚀 คู่มือการติดตั้ง Flutter

> คู่มือการติดตั้ง Flutter SDK สำหรับระบบปฏิบัติการ Windows และ macOS

เอกสารฉบับนี้จัดทำขึ้นเพื่อแนะนำขั้นตอนการติดตั้ง Flutter SDK สำหรับการพัฒนาแอปพลิเคชันข้ามแพลตฟอร์มบนระบบปฏิบัติการ Windows และ macOS อย่างเป็นลำดับขั้น

## 📋 ภาพรวมกระบวนการติดตั้ง

กระบวนการติดตั้ง Flutter ประกอบด้วยขั้นตอนหลักดังต่อไปนี้:

1. **ดาวน์โหลดชุดพัฒนาซอฟต์แวร์ (Flutter SDK)**: การรับชุดเครื่องมือหลักของ Flutter
2. **การตั้งค่าตัวแปรสภาพแวดล้อม (Environment Variables)**: เพื่อให้ระบบปฏิบัติการรู้จักคำสั่ง `flutter` จาก Command Line Interface (CLI)
3. **การติดตั้งซอฟต์แวร์ที่จำเป็น**: ติดตั้ง Android Studio สำหรับการพัฒนาบน Android และ/หรือ Xcode สำหรับการพัฒนาบน iOS
4. **การตรวจสอบความสมบูรณ์ของการติดตั้ง**: ใช้เครื่องมือ `flutter doctor` เพื่อยืนยันว่าการตั้งค่าทั้งหมดถูกต้อง

## 💻 การติดตั้งบนระบบปฏิบัติการ Windows

### ขั้นตอนที่ 1: ดาวน์โหลด Flutter SDK

1. เข้าถึงเว็บไซต์อย่างเป็นทางการของ Flutter: [https://flutter.dev/docs/get-started/install/windows](https://flutter.dev/docs/get-started/install/windows)
2. ดำเนินการดาวน์โหลด Flutter SDK สำหรับ Windows ซึ่งเป็นไฟล์ `.zip` เวอร์ชันล่าสุด (Stable)

### ขั้นตอนที่ 2: การแตกไฟล์และจัดเก็บ

1. แตกไฟล์ (Extract) `.zip` ที่ดาวน์โหลดมา จะปรากฏโฟลเดอร์ชื่อ `flutter`
2. ย้ายโฟลเดอร์ `flutter` ไปยังตำแหน่งที่ไม่มีข้อจำกัดด้านสิทธิ์การเข้าถึง (Permissions) เช่น `C:\src\flutter`

> ⚠️ **ข้อควรระวัง**: โปรดหลีกเลี่ยงการติดตั้งในไดเรกทอรีที่ต้องการสิทธิ์ผู้ดูแลระบบ (Administrator) เช่น `C:\Program Files\` เพื่อป้องกันปัญหาที่อาจเกิดขึ้น

### ขั้นตอนที่ 3: การตั้งค่า Environment Path

1. ในช่องค้นหาของ Windows Search พิมพ์คำว่า `env` และเลือก "Edit the system environment variables"
2. ในหน้าต่าง System Properties คลิกที่ปุ่ม "Environment Variables..."
3. ภายใต้หัวข้อ "User variables" เลือกตัวแปร `Path` และคลิก "Edit..."
4. คลิก "New" และเพิ่มพาธ (Path) ไปยังไดเรกทอรี `bin` ภายในโฟลเดอร์ flutter ของท่าน ตัวอย่างเช่น: `C:\src\flutter\bin`
5. คลิก "OK" เพื่อบันทึกการเปลี่ยนแปลงในทุกหน้าต่างที่เปิดอยู่

### ขั้นตอนที่ 4: การติดตั้ง Android Studio

1. ดาวน์โหลดโปรแกรมติดตั้ง Android Studio จาก: [https://developer.android.com/studio](https://developer.android.com/studio)
2. ดำเนินการติดตั้งตามคำแนะนำบนหน้าจอ โปรแกรมจะทำการติดตั้งเครื่องมือที่จำเป็น เช่น Android SDK และ Command-line Tools โดยอัตโนมัติในการเปิดใช้งานครั้งแรก

### ขั้นตอนที่ 5: การตรวจสอบความสมบูรณ์ด้วย flutter doctor

1. เปิดโปรแกรม Command Prompt หรือ PowerShell ขึ้นมาใหม่
2. รันคำสั่งดังต่อไปนี้:

```bash
flutter doctor
```

3. เครื่องมือ `flutter doctor` จะวิเคราะห์และแสดงรายงานสถานะการติดตั้ง หากพบข้อผิดพลาดหรือส่วนที่ยังไม่ได้ตั้งค่า (ระบุด้วยสัญลักษณ์ [!]) ให้ดำเนินการตามคำแนะนำที่แสดงผล

4. ในกรณีที่พบข้อผิดพลาดเกี่ยวกับใบอนุญาตของ Android (Android licenses) ให้รันคำสั่ง:

```bash
flutter doctor --android-licenses
```

จากนั้นกด `y` เพื่อยอมรับข้อตกลงทั้งหมด

5. รัน `flutter doctor` อีกครั้งเพื่อยืนยันว่าปัญหาได้รับการแก้ไข และสถานะของ Flutter และ Android toolchain แสดงเป็นเครื่องหมาย [✓]

## 🍎 การติดตั้งบนระบบปฏิบัติการ macOS

### ขั้นตอนที่ 1: ดาวน์โหลด Flutter SDK

1. เข้าถึงเว็บไซต์: [https://flutter.dev/docs/get-started/install/macos](https://flutter.dev/docs/get-started/install/macos)
2. เลือกดาวน์โหลด Flutter SDK สำหรับสถาปัตยกรรมของเครื่องท่าน (Apple Silicon หรือ Intel)

### ขั้นตอนที่ 2: การแตกไฟล์และจัดเก็บ

1. แตกไฟล์ `.zip` ที่ดาวน์โหลดมา จะปรากฏโฟลเดอร์ `flutter`
2. ย้ายโฟลเดอร์ `flutter` ไปยังไดเรกทอรีที่ต้องการ เช่น `/Users/[Your Username]/development/flutter`

### ขั้นตอนที่ 3: การตั้งค่า Path

1. เปิดโปรแกรม Terminal
2. เปิดไฟล์คอนฟิกูเรชันของ Shell ด้วยคำสั่ง (สำหรับ Zsh ซึ่งเป็น Shell เริ่มต้นของ macOS รุ่นใหม่):

```bash
nano ~/.zshrc
```

3. เพิ่มบรรทัดต่อไปนี้ที่ส่วนท้ายสุดของไฟล์ โดยแทนที่ `[PATH_TO_FLUTTER_DIRECTORY]` ด้วยพาธจริงของโฟลเดอร์ flutter ของท่าน:

```bash
export PATH="$PATH:[PATH_TO_FLUTTER_DIRECTORY]/bin"
```

**ตัวอย่าง:**

```bash
export PATH="$PATH:/Users/YourUsername/development/flutter/bin"
```

4. บันทึกการเปลี่ยนแปลงโดยกด `Control + X`, พิมพ์ `Y`, และกด `Enter`
5. ปิดและเปิด Terminal ใหม่อีกครั้งเพื่อให้การตั้งค่ามีผลบังคับใช้

### ขั้นตอนที่ 4: การติดตั้ง Xcode และ Android Studio

#### Xcode
>
> จำเป็นสำหรับการพัฒนาและคอมไพล์แอปพลิเคชันสำหรับ iOS และ macOS

1. ติดตั้ง Xcode จาก Mac App Store
2. หลังจากติดตั้งเสร็จสิ้น ให้รันคำสั่งต่อไปนี้ใน Terminal เพื่อกำหนดค่าที่จำเป็น:

```bash
sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
sudo xcodebuild -runFirstLaunch
```

#### Android Studio

1. ดาวน์โหลดและติดตั้งจาก: [https://developer.android.com/studio](https://developer.android.com/studio)

### ขั้นตอนที่ 5: การตรวจสอบความสมบูรณ์ด้วย flutter doctor

1. เปิด Terminal ขึ้นมาใหม่
2. รันคำสั่ง:

```bash
flutter doctor
```

3. ตรวจสอบผลลัพธ์และปฏิบัติตามคำแนะนำเพื่อแก้ไขส่วนที่ยังไม่สมบูรณ์ เช่น การติดตั้ง CocoaPods หากจำเป็น:

```bash
sudo gem install cocoapods
```

4. รัน `flutter doctor` ซ้ำจนกว่าสถานะของ Flutter, Android toolchain, และ Xcode จะแสดงเป็น [✓] ทั้งหมด

---

## 🎉 สรุป

หลังจากทำตามขั้นตอนทั้งหมดแล้ว คุณจะสามารถใช้งาน Flutter เพื่อพัฒนาแอปพลิเคชันข้ามแพลตฟอร์มได้อย่างสมบูรณ์ การติดตั้งที่ถูกต้องจะช่วยให้กระบวนการพัฒนาเป็นไปอย่างราบรื่นและมีประสิทธิภาพ

สำหรับข้อมูลเพิ่มเติมและคู่มือการใช้งาน สามารถเยี่ยมชมเว็บไซต์อย่างเป็นทางการได้ที่: [https://flutter.dev](https://flutter.dev)
