# 🛒 GoCart - แพลตฟอร์ม E-commerce ครบครัน

> **Credit:** โปรเจกต์นี้สร้างขึ้นตามการสอนจากวิดีโอ YouTube: [Build Modern E-commerce with Next.js](https://youtu.be/aYu4xkBdkNA?si=6BpxBS_SnZrAyPFD)

GoCart เป็นแพลตฟอร์ม E-commerce สมัยใหม่ที่สร้างด้วย Next.js รองรับระบบ Multi-vendor และมีฟีเจอร์ครบครัน พร้อมระบบการจัดการที่ทรงพลัง

## ✨ ฟีเจอร์หลัก

### 🏪 สำหรับลูกค้า
- **หน้าแรกที่ทันสมัย** - Hero Section, Best Selling, Latest Products
- **ระบบค้นหาและกรองสินค้า** - ค้นหาสินค้าได้ง่ายและรวดเร็ว
- **ระบบตะกร้าสินค้า** - จัดการสินค้าในตะกร้าแบบเรียลไอม์
- **ระบบที่อยู่จัดส่ง** - เพิ่ม/แก้ไขที่อยู่ได้หลายรายการ
- **ระบบคูปองส่วนลด** - ใช้คูปองส่วนลดได้
- **การชำระเงินหลายช่องทาง** - COD และ Stripe Payment
- **ระบบสมาชิกพิเศษ Plus** - ฟรีค่าจัดส่งและสิทธิพิเศษ
- **ระบบรีวิวและการให้คะแนน** - รีวิวสินค้าหลังซื้อ
- **ประวัติการสั่งซื้อ** - ติดตามสถานะคำสั่งซื้อ

### 🏬 สำหรับร้านค้า (Multi-vendor)
- **หน้าแดชบอร์ดร้านค้า** - จัดการร้านค้าแบบครบวงจร
- **เพิ่ม/แก้ไขสินค้า** - อัปโหลดรูปภาพและจัดการข้อมูลสินค้า
- **จัดการคำสั่งซื้อ** - อัปเดตสถานะคำสั่งซื้อ
- **ระบบการอนุมัติร้านค้า** - ระบบตรวจสอบก่อนเปิดร้าน

### 👨‍💼 สำหรับผู้ดูแลระบบ (Admin)
- **แดชบอร์ดแอดมิน** - ภาพรวมการขาย Charts และสถิติ
- **อนุมัติร้านค้าใหม่** - ตรวจสอบและอนุมัติร้านค้า
- **จัดการคูปอง** - สร้างและจัดการคูปองส่วนลด
- **จัดการร้านค้า** - ดูข้อมูลและสถานะร้านค้าทั้งหมด

## 🛠 เทคโนโลยีที่ใช้

### Frontend
- **Next.js 15** - React Framework แบบ Full-stack
- **React 19** - UI Library เวอร์ชั่นล่าสุด
- **Tailwind CSS** - CSS Framework สำหรับ Styling
- **Redux Toolkit** - State Management
- **Lucide React** - ไอคอนสวยงาม

### Backend
- **Next.js API Routes** - RESTful API endpoints
- **Prisma ORM** - Database ORM และ Schema management
- **NeonDB (PostgreSQL)** - Cloud Database
- **Clerk Authentication** - ระบบล็อกอิน/สมัครสมาชิก

### Third-party Services
- **ImageKit** - การอัปโหลดและจัดการรูปภาพ
- **Stripe** - ระบบชำระเงิน
- **OpenAI API** - ฟีเจอร์ AI (ถ้ามี)
- **Inngest** - Background Jobs และ Webhooks
- **React Hot Toast** - การแจ้งเตือน

## 📦 การติดตั้ง

### 1. Clone Repository
```bash
git clone https://github.com/yourusername/gocart-ecommerce.git
cd gocart-ecommerce
```

### 2. ติดตั้ง Dependencies
```bash
npm install
# หรือ
yarn install
```

### 3. ตั้งค่า Environment Variables
สร้างไฟล์ `.env.local` และเพิ่มตัวแปรต่อไปนี้:

```env
# Database
DATABASE_URL="your_neon_database_url"
DIRECT_URL="your_direct_database_url"

# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY="your_clerk_publishable_key"
CLERK_SECRET_KEY="your_clerk_secret_key"
NEXT_PUBLIC_CLERK_SIGN_IN_URL="/sign-in"
NEXT_PUBLIC_CLERK_SIGN_UP_URL="/sign-up"

# ImageKit
IMAGEKIT_PUBLIC_KEY="your_imagekit_public_key"
IMAGEKIT_PRIVATE_KEY="your_imagekit_private_key"
IMAGEKIT_URL_ENDPOINT="your_imagekit_url_endpoint"

# Stripe
STRIPE_SECRET_KEY="your_stripe_secret_key"
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY="your_stripe_publishable_key"

# OpenAI (ถ้าใช้)
OPENAI_API_KEY="your_openai_api_key"
OPENAI_BASE_URL="https://api.openai.com/v1"

# Admin Email
ADMIN_EMAIL="admin@example.com"

# Currency
NEXT_PUBLIC_CURRENCY_SYMBOL="$"
```

### 4. ตั้งค่า Database
```bash
# Generate Prisma Client
npx prisma generate

# Push schema to database
npx prisma db push
```

### 5. เรียกใช้โปรเจกต์
```bash
npm run dev
# หรือ
yarn dev
```

เปิดเบราว์เซอร์ไปที่ [http://localhost:3000](http://localhost:3000)

## 📁 โครงสร้างโปรเจกต์

```
gocart/
├── app/                    # Next.js App Router
│   ├── (pages)/           # หน้าต่างๆ ของเว็บไซต์
│   ├── admin/             # หน้าแอดมิน
│   ├── store/             # หน้าร้านค้า
│   ├── api/               # API Routes
│   └── globals.css        # Global styles
├── components/            # React Components
│   ├── admin/             # Components สำหรับแอดมิน
│   └── store/             # Components สำหรับร้านค้า
├── lib/                   # Utilities และ configurations
│   ├── features/          # Redux slices
│   ├── prisma.js          # Prisma client
│   └── store.js           # Redux store
├── prisma/                # Database schema
├── configs/               # Configuration files
├── middlewares/           # Custom middlewares
└── inngest/               # Background jobs
```

## 🚀 การใช้งาน

### สำหรับลูกค้า
1. **สมัครสมาชิก/เข้าสู่ระบบ** ผ่าน Clerk
2. **เลือกซื้อสินค้า** จากหน้าแรกหรือหน้า Shop
3. **เพิ่มสินค้าในตะกร้า** และปรับจำนวน
4. **เพิ่มที่อยู่จัดส่ง** ในหน้าตะกร้า
5. **เลือกวิธีการชำระเงิน** COD หรือ Stripe
6. **ใช้คูปองส่วนลด** (ถ้ามี)
7. **ติดตามสถานะคำสั่งซื้อ** ในหน้า Orders

### สำหรับร้านค้า
1. **สมัครสมาชิก** และสมัครเป็นผู้ขาย
2. **รอการอนุมัติ** จากผู้ดูแลระบบ
3. **เข้าสู่หน้าร้านค้า** ที่ `/store`
4. **เพิ่มสินค้า** และจัดการสต๊อก
5. **จัดการคำสั่งซื้อ** อัปเดตสถานะ

### สำหรับแอดมิน
1. **เข้าสู่ระบบ** ด้วยอีเมลแอดมิน
2. **เข้าสู่หน้าแอดมิน** ที่ `/admin`
3. **อนุมัติร้านค้าใหม่** ในหน้า Approve Store
4. **สร้างคูปองส่วนลด** ในหน้า Coupons
5. **ดูสถิติการขาย** ในหน้า Dashboard

## 🎨 การปรับแต่ง

### เปลี่ยนธีมสี
แก้ไขไฟล์ `app/globals.css` และ Tailwind configuration

### เพิ่มฟีเจอร์ใหม่
1. สร้าง API Route ใน `app/api/`
2. เพิ่ม Redux slice ใน `lib/features/`
3. สร้าง Component ใน `components/`

### เปลี่ยน Currency
แก้ไข `NEXT_PUBLIC_CURRENCY_SYMBOL` ในไฟล์ `.env`

## 🐛 การแก้ไขปัญหา

### ปัญหาที่พบบ่อย
1. **Database connection error**: ตรวจสอบ DATABASE_URL
2. **ImageKit upload failed**: ตรวจสอบ API keys ของ ImageKit
3. **Clerk authentication error**: ตรวจสอบ Clerk configuration
4. **Stripe payment failed**: ตรวจสอบ Stripe keys และ webhooks

## 🤝 การมีส่วนร่วม

1. Fork โปรเจกต์
2. สร้าง feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit การเปลี่ยนแปลง (`git commit -m 'Add some AmazingFeature'`)
4. Push ไปยัง branch (`git push origin feature/AmazingFeature`)
5. เปิด Pull Request

## 📄 License

โปรเจกต์นี้อยู่ภายใต้ MIT License - ดู [LICENSE](LICENSE) file สำหรับรายละเอียด

## 🙏 ขอบคุณ

- **คุณครู/ผู้สอน** ที่สร้างวิดีโอสอนที่ยอดเยี่ยม
- **Vercel** สำหรับ hosting
- **Neon** สำหรับ PostgreSQL database
- **Clerk** สำหรับ authentication service
- **Stripe** สำหรับ payment processing

**🎥 Credit:** [Build Modern E-commerce with Next.js - YouTube Tutorial](https://youtu.be/aYu4xkBdkNA?si=6BpxBS_SnZrAyPFD)
