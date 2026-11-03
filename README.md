# Bank DApp (MAT 231 Discrete Mathematics – Assignment)

เว็บ DApp สำหรับใช้งาน Smart Contract ระบบธนาคาร (Deposit / Withdraw / CheckBalance) เชื่อมต่อผ่าน MetaMask

- **รหัสนักศึกษา:** 66048395
- **ชื่อ-สกุล:** อารยา โฆษิตไกร
- **มหาวิทยาลัย:** มหาวิทยาลัยศรีปทุม – คณะเทคโนโลยีสารสนเทศ
- **เว็บ DApp (GitHub Pages):** https://arayakositkrai.github.io/SmartContractAssignment8Araya/
- **Smart Contract:** [Bank.sol](./Bank.sol)
- **Contract address (Sepolia):** 0xa01dd53713C4422AD9038306fdfDCa3b4A7BC56d

## ฟีเจอร์

- **เชื่อมต่อ Smart Contract:** ใช้ ethers.js (v6) เรียก contract ตาม ABI ที่กำหนด
- **เชื่อมต่อ MetaMask:** ปุ่ม Connect Wallet ขอสิทธิ์บัญชีและสลับไปเครือข่าย Sepolia อัตโนมัติ
- **Deposit:** กรอกจำนวน ETH แล้วกด Deposit เพื่อเรียก deposit() (payable)
- **Withdraw:** กรอกจำนวน ETH แล้วกด Withdraw เพื่อเรียก withdraw(amount)
- **CheckBalance:** กด CheckBalance เพื่อเรียก checkBlance() แสดงยอดเงินของบัญชีที่เชื่อมต่อ
- **แสดงข้อมูลผู้ทำ:** ส่วนหัวของหน้าเว็บแสดงรหัสนักศึกษาและชื่อ-สกุล

## โครงสร้างไฟล์

- Bank.sol : Smart Contract (Solidity ^0.8.0)
- index.html : หน้าเว็บ DApp (HTML + CSS + JS ไฟล์เดียว)
- README.md : เอกสารนี้

## Smart Contract

Bank.sol เก็บยอดเงินของแต่ละ address ใน mapping(address => uint) _balances

- deposit() รับ ETH (msg.value ต้องมากกว่า 0) บวกยอดและ emit Deposit
- withdraw(uint amount) ตรวจว่ายอดพอ โอน ETH คืนผู้เรียก ลดยอดและ emit Withdraw
- checkBlance() เป็น view คืนยอดเงินของ msg.sender

หมายเหตุ: ชื่อฟังก์ชัน checkBlance สะกดตามโจทย์ที่กำหนดให้

## วิธี Deploy Contract

1. เปิด Remix IDE (https://remix.ethereum.org) สร้างไฟล์ Bank.sol แล้ววางโค้ดจาก repo นี้
2. Compile ด้วย Solidity 0.8.x
3. แท็บ Deploy & Run เลือก Environment เป็น Injected Provider – MetaMask (เครือข่าย Sepolia)
4. กด Deploy แล้วคัดลอก contract address ไปใส่ใน CONTRACT_ADDRESS ของ index.html

## วิธีใช้งานเว็บ

1. ติดตั้งส่วนขยาย MetaMask และมี Sepolia ETH (ขอได้จาก faucet)
2. เปิดเว็บ DApp ตามลิงก์ด้านบน แล้วกด Connect Wallet
3. กรอกจำนวน ETH แล้วกด Deposit หรือ Withdraw และยืนยันใน MetaMask
4. กด CheckBalance เพื่อดูยอดเงินปัจจุบัน

## วิธีนำขึ้น GitHub Pages

1. ไปที่ Settings > Pages
2. Source: Deploy from a branch, Branch: main / (root) แล้วกด Save
3. รอสักครู่ จะได้ URL https://USERNAME.github.io/REPO/

## เทคโนโลยี

Solidity, ethers.js v6, MetaMask, HTML/CSS/JavaScript, GitHub Pages
