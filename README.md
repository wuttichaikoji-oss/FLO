# Laya Multi Department Task App v1.0

ระบบใหม่แยกออกจาก HK Task เดิม เพื่อเก็บ HK Task เดิมเป็น backup

## Roles
- Manager
- FO
- HK
- FB
- ENG
- Supervisor HK
- Supervisor FB
- Supervisor ENG

## Flow
- FO เปิดงานและเลือกแผนกปลายทาง HK / FB / ENG
- Supervisor ของแต่ละแผนก assign งานภายในแผนกตัวเอง
- แผนกปลายทางทำงานแบบเดียวกับ HK เดิม
- FO ปิดงานแล้วงานจะย้ายไป LOG

## Pages
- manager.html
- fo.html
- hk.html
- fb.html
- eng.html
- supervisor-hk.html
- supervisor-fb.html
- supervisor-eng.html
- board.html
- log.html

## Firebase Collections
- multi_dept_tasks_v1
- multi_dept_logs_v1
- multi_dept_users_v1
- device_tokens

## Firestore Rules ที่ต้องมีเพิ่ม
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /multi_dept_tasks_v1/{document} { allow read, write: if true; }
    match /multi_dept_logs_v1/{document} { allow read, write: if true; }
    match /multi_dept_users_v1/{document} { allow read, write: if true; }
    match /device_tokens/{document} { allow read, write: if true; }
  }
}

## Default Login
- FO A = 1001
- HK A = 2001
- FB A = 3001
- ENG A = 4001
- Supervisor HK = 9100
- Supervisor FB = 9200
- Supervisor ENG = 9300
- Manager = 9900
