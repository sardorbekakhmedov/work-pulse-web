# work-pulse-web

# 🏢 Frontend (Angular Client)

## 🏗 Arxitektura va Dizayn

Tizim **Micro-frontend** tamoyillariga asoslangan, lekin monolith repo ichida boshqariladigan **Standalone Components** arxitekturasida quriladi.

- **Framework:** Angular 17+ (Signals-based reactivity).
- **Styling:** Tailwind CSS + PostCSS (Custom utilities uchun).
- **State Management:** **Angular Signals** (Local state) va **NgRx Signal Store** (Global state).
- **UI Library:** **Angular Material** + **Lucide Icons** (Zamonaviy va yengil ikonkalari uchun).

---

## 📂 Papkalar Strukturasi (Scalable Folder Structure)

Loyiha kengayishiga moslashgan, **Feature-first** yondashuvidagi tuzilma:

- `src/app/core/`:
    - `interceptors/`: `auth.interceptor.ts`, `error.interceptor.ts`.
    - `guards/`: `auth.guard.ts`, `role.guard.ts`.
    - `services/`: `api.service.ts`, `auth.service.ts`.
- `src/app/shared/`:
    - `components/`: `dynamic-table`, `confirm-dialog`, `status-badge`.
    - `directives/`: `has-role.directive.ts`.
    - `pipes/`: `currency-uzb.pipe.ts`.
- `src/app/features/`:
    - `auth/`: Login, Reset password.
    - `dashboard/`: HR uchun asosiy statistika.
    - `employees/`: Ro'yxat, profil, xodim kartochkasi.
    - **`payroll/`**: Ish haqi hisoblash, bonuslar, jarimalar.
    - **`performance/`**: KPI ko'rsatkichlari va baholash tizimi.
- `src/app/store/`: `user.store.ts`, `config.store.ts`.

---

## 🛠 Asosiy Funksiyalar va Kengaytirishlar

1. **Global Error Handling**: Har bir API xatosini foydalanuvchiga chiroyli **Snackbar** orqali bildirish.
2. **Dynamic Permissions**: Foydalanuvchi roliga qarab (`Admin`, `Manager`, `Employee`) menyularni va tugmalarni yashirish/ko'rsatish.
3. **PDF/Excel Export**: Xodimlar ro'yxati va Payroll ma'lumotlarini yuklab olish (Library: `xlsx`, `jspdf`).
4. **Skeleton Loaders**: Ma'lumot yuklanayotgan paytda foydalanuvchi tajribasini (UX) yaxshilash.

---

## 🎨 UI/UX Standartlari (Enterprise Design)

- **Colors:**
    - *Primary:* `#1E40AF` (Deep Blue) – Ishonch va barqarorlik.
    - *Secondary:* `#64748B` (Slate) – Neytral matnlar uchun.
    - *Success:* `#10B981` (Emerald) – Tasdiqlash uchun.
- **Interaktivlik:**
    - Barcha inputlarda **Floating labels** ishlatiladi.
    - Jadvallarda **"Sticky Header"** va **"Drag & Drop"** (Angular CDK) imkoniyati.

---

## 📋 Modullar Tavsifi (Yangi qo'shilganlar)

| **Modul** | **Vazifasi** | **Asosiy komponentlar** |
| --- | --- | --- |
| **Employees** | Xodimlarning shaxsiy va mehnat ma'lumotlari. | `EmployeeList`, `EmployeeProfile`, `ContractDetails` |
| **Payroll** | Oylik maosh, soliqlar va avans hisoboti. | `SalaryCalculator`, `PaySlip`, `BonusManager` |
| **Performance** | Xodimlarni choraklik baholash (KPI). | `KpiDashboard`, `ReviewForm`, `RatingSystem` |

---

## 🚀 Ishga tushirish va O'rnatish

1. **Node.js**: v18.10.0 yoki undan yuqori.
2. **CLI o'rnatish**: `npm install -g @angular/cli`.
3. **Loyiha dependencylari**:Bash
    
    `npm install
    npm install -D tailwindcss postcss autoprefixer
    npm install @angular/material @angular/cdk`
    
4. **Environment sozlash**: `src/environments/` ichida API URL larni ko'rsatish.
5. **Start**: `ng serve --port 4200`.
