# HCMUT SAMS (Smart Asset Management System)

A comprehensive full-stack application for managing equipment, assets, and booking workflows at Ho Chi Minh City University of Technology (HCMUT).

## 🚀 Features (In Development)

- **Authentication & Authorization**: Secure login, OTP verification, Role-Based Access Control (RBAC).
- **Equipment & Asset Management**: Track and manage the university's assets efficiently.
- **Booking & Rental Workflow**: Seamless equipment reservation with automatic conflict checking.
- **Automated Notifications**: Email alerts for verification, reset passwords, and booking statuses.
- **Payment Integration**: VNPAY support for handling rental/payment transactions.

## 🛠 Tech Stack

### Frontend
- **Framework**: [React 19](https://react.dev/) with [Vite](https://vitejs.dev/)
- **Styling**: [Tailwind CSS 4](https://tailwindcss.com/) & [Radix UI](https://www.radix-ui.com/) (shadcn/ui-like)
- **State Management**: [Redux Toolkit](https://redux-toolkit.js.org/)
- **Routing**: [React Router](https://reactrouter.com/)
- **Charts / UI**: Recharts, Lucide React, Day.js

### Backend
- **Framework**: [NestJS 11](https://nestjs.com/) (TypeScript)
- **Database**: [MongoDB](https://www.mongodb.com/) via [Mongoose](https://mongoosejs.com/)
- **Authentication**: JWT, [Passport.js](https://www.passportjs.org/) (Local, JWT & Google OAuth20)
- **Email**: Nodemailer for transactional emails

## 📂 Project Structure

```text
HCMUT_SAMS/
│
├── Backend/                             # NestJS Backend Application
│   ├── src/
│   │   ├── common/                      # DTOs, Enums, Interfaces, Guards, Decorators
│   │   ├── modules/                     # Feature Modules (Core Business Logic)
│   │   │   ├── admin/                   # Admin management & system configuration
│   │   │   ├── auth/                    # Authentication (Login, Register, OTP, JWT)
│   │   │   ├── booking/                 # Booking system for rooms/facilities
│   │   │   ├── checkin/                 # Check-in/Check-out operations
│   │   │   ├── equipment/               # Equipment catalog and types
│   │   │   ├── equipment-Rental/        # Equipment rental workflows
│   │   │   ├── equipment-item/          # Specific equipment items (Inventory)
│   │   │   ├── facility/                # Physical facilities (Buildings, Rooms)
│   │   │   ├── history/                 # Audit logs and transaction history
│   │   │   ├── notification/            # Email and system notifications
│   │   │   ├── payment/                 # VNPAY integration
│   │   │   └── users/                   # User profiles and Management
│   │   └── main.ts                      # Application entry point
│   └── package.json
│
└── Frontend/                            # React + Vite Frontend Application
    ├── src/
    │   ├── assets/                      # Static files (images, fonts)
    │   ├── components/                  # Reusable UI components (Buttons, Inputs, etc.)
    │   ├── constants/                   # Application-wide constants
    │   ├── hooks/                       # Custom React hooks (Redux hooks, etc.)
    │   ├── layout/                      # Page layout components (Navbar, Sidebar)
    │   ├── lib/                         # Utility libraries and configurations
    │   ├── pages/                       # Route components (Home, Login, Dashboard)
    │   ├── routes/                      # Route definitions
    │   ├── services/                    # API services for backend communication
    │   ├── store/                       # Redux store slices setup
    │   ├── types/                       # TypeScript interfaces/types
    │   └── utils/                       # Helper functions
    └── package.json
```

## ⚙️ Getting Started

### Prerequisites

- Node.js (v18 or higher recommended)
- MongoDB running locally or accessible via URI
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd HCMUT_SAMS
   ```

2. **Backend Setup**
   ```bash
   cd Backend
   npm install
   # Configure your environment variables in a .env file
   npm run start:dev
   ```

3. **Frontend Setup**
   ```bash
   cd ../Frontend
   npm install
   # Configure your environment variables in a .env file if necessary
   npm run dev
   ```

## 🧪 Test Data & Credentials

### System Admin Account
For administrative access to the system:
- **📧 Email**: `admin@hcmut.edu.vn`
- **🔑 Password**: `Admin@123456`

### VNPAY Payment Sandbox Information
Use the following sandbox credentials to test the checkout/payment integrations securely:

| Trường / Field | Giá trị / Value |
| :--- | :--- |
| **Ngân hàng (Bank)** | `NCB` |
| **Số thẻ (Card Number)** | `9704198526191432198` |
| **Tên chủ thẻ (Cardholder Name)** | `NGUYEN VAN A` |
| **Ngày phát hành (Issue Date)** | `07/15` |
| **Mật khẩu OTP (OTP Password)** | `123456` |

## 🛡️ Best Practices & Security
- Passwords are encrypted using `bcrypt`.
- Email verifications and OTPs are utilized for sensitive account operations.
- Avoid committing actual `.env` files.
