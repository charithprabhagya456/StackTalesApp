# StackTales Frontend - Next.js Integration

## Overview

This is the frontend application for StackTales, built with Next.js 15, TypeScript, Tailwind CSS, and shadcn/ui components. It's fully integrated with the StackTales backend API.

## 🚀 Features

- **Modern Tech Stack**: Next.js 15, TypeScript, Tailwind CSS v4
- **UI Components**: shadcn/ui with Radix UI primitives
- **Authentication**: Complete login/register system with JWT tokens
- **Responsive Design**: Mobile-first, responsive layout
- **Form Validation**: React Hook Form with Zod schema validation
- **State Management**: React Context for authentication state
- **API Integration**: Full integration with StackTales backend

## 🛠️ Tech Stack

- **Framework**: Next.js 15 with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS v4
- **UI Components**: shadcn/ui + Radix UI
- **Forms**: React Hook Form + Zod validation
- **Icons**: Lucide React
- **State**: React Context API
- **HTTP Client**: Native fetch API

## 📁 Project Structure

```
src/
├── app/                    # Next.js App Router
│   ├── auth/              # Authentication pages
│   ├── dashboard/         # Dashboard pages
│   ├── globals.css        # Global styles
│   ├── layout.tsx         # Root layout
│   └── page.tsx           # Home page
├── components/            # Reusable components
│   ├── auth/              # Authentication components
│   └── ui/                # shadcn/ui components
├── contexts/              # React contexts
├── hooks/                 # Custom hooks
├── lib/                   # Utilities and API client
└── types/                 # TypeScript type definitions
```

## 🔧 Setup & Installation

### Prerequisites

- Node.js 18+ 
- npm or yarn
- StackTales backend running on port 3000

### Installation

1. **Install dependencies**:
   ```bash
   npm install
   ```

2. **Set up environment variables**:
   ```bash
   cp .env.local.example .env.local
   ```
   
   Update `.env.local` with your backend API URL:
   ```env
   NEXT_PUBLIC_API_URL=http://localhost:3000/api
   ```

3. **Start development server**:
   ```bash
   npm run dev
   ```

4. **Open your browser**:
   Navigate to [http://localhost:3001](http://localhost:3001)

## 🔐 Authentication System

### Features

- **User Registration**: Create new accounts with validation
- **User Login**: Secure authentication with email/password
- **JWT Tokens**: Automatic token management
- **Protected Routes**: Route protection based on auth status
- **Persistent Sessions**: Tokens stored in localStorage

### Authentication Flow

1. **Registration**: User fills out form → API call → Account created → Auto-login
2. **Login**: User enters credentials → API call → Token received → Dashboard access
3. **Session Management**: Token automatically included in API requests
4. **Logout**: Token cleared → Redirected to auth page

### Protected Routes

- `/dashboard` - Requires authentication
- `/auth` - Redirects authenticated users to dashboard
- `/` - Redirects based on auth status

## 🎨 UI Components

### shadcn/ui Components Used

- **Button**: Various button variants and sizes
- **Card**: Content containers with headers
- **Input**: Form input fields
- **Label**: Form labels
- **Alert**: Error and success messages
- **Avatar**: User profile pictures
- **Badge**: Status indicators
- **Separator**: Visual dividers

### Custom Components

- **LoginForm**: User authentication form
- **RegisterForm**: User registration form
- **AuthPage**: Authentication page with form switching
- **DashboardPage**: Main user dashboard

## 🔌 API Integration

### API Client

The frontend uses a centralized API client (`src/lib/api.ts`) that provides:

- **Base Configuration**: Configurable API URL
- **Authentication**: Automatic token inclusion
- **Error Handling**: Consistent error responses
- **Type Safety**: Full TypeScript support

### API Endpoints

- `POST /api/users/register` - User registration
- `POST /api/users/login` - User authentication
- `GET /api/users` - Get user list (paginated)
- `GET /api/users/:id` - Get specific user
- `PUT /api/users/:id` - Update user
- `DELETE /api/users/:id` - Delete user

### Request/Response Types

All API interactions are fully typed with TypeScript interfaces:

```typescript
interface User {
  _id: string;
  email: string;
  username: string;
  firstName?: string;
  lastName?: string;
  isActive: boolean;
  lastLogin?: string;
  createdAt: string;
  updatedAt: string;
}
```

## 📱 Responsive Design

### Breakpoints

- **Mobile**: < 640px (default)
- **Tablet**: 640px - 1024px
- **Desktop**: > 1024px

### Layout Features

- **Grid System**: CSS Grid for complex layouts
- **Flexbox**: Flexbox for component alignment
- **Mobile First**: Mobile-optimized design
- **Touch Friendly**: Optimized for touch devices

## 🎯 Key Features

### Dashboard

- **User Profile**: Display user information
- **Quick Stats**: Account statistics
- **Quick Actions**: Common user actions
- **Responsive Layout**: Adapts to screen size

### Forms

- **Validation**: Real-time form validation
- **Error Handling**: User-friendly error messages
- **Loading States**: Visual feedback during submission
- **Accessibility**: ARIA labels and keyboard navigation

## 🚀 Development

### Available Scripts

```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server
npm run lint         # Run ESLint
```

### Development Workflow

1. **Feature Development**: Create components in `src/components/`
2. **API Integration**: Update `src/lib/api.ts` for new endpoints
3. **State Management**: Use React Context for global state
4. **Styling**: Use Tailwind CSS classes and shadcn/ui components
5. **Testing**: Test components and API integration

### Code Quality

- **TypeScript**: Strict type checking enabled
- **ESLint**: Code quality and consistency
- **Prettier**: Code formatting
- **Component Structure**: Consistent component patterns

## 🔒 Security Features

- **Input Validation**: Client and server-side validation
- **Token Management**: Secure token storage and handling
- **Protected Routes**: Authentication-based access control
- **CORS Handling**: Proper cross-origin request handling

## 🌐 Environment Configuration

### Development

```env
NEXT_PUBLIC_API_URL=http://localhost:3000/api
NODE_ENV=development
```

### Production

```env
NEXT_PUBLIC_API_URL=https://api.stacktales.com/api
NODE_ENV=production
```

## 📊 Performance

- **Next.js Optimization**: Built-in performance optimizations
- **Code Splitting**: Automatic route-based code splitting
- **Image Optimization**: Next.js Image component
- **Bundle Analysis**: Built-in bundle analyzer

## 🧪 Testing

### Testing Strategy

- **Unit Tests**: Component testing with React Testing Library
- **Integration Tests**: API integration testing
- **E2E Tests**: End-to-end user flow testing

### Running Tests

```bash
npm run test          # Run unit tests
npm run test:e2e      # Run end-to-end tests
npm run test:coverage # Run tests with coverage
```

## 🚀 Deployment

### Build Process

1. **Development**: `npm run dev` for local development
2. **Build**: `npm run build` for production build
3. **Start**: `npm run start` for production server

### Deployment Options

- **Vercel**: Recommended for Next.js apps
- **Netlify**: Alternative deployment platform
- **Self-hosted**: Docker or traditional hosting

## 🔧 Troubleshooting

### Common Issues

1. **API Connection Failed**
   - Check backend server is running
   - Verify API URL in `.env.local`
   - Check CORS configuration

2. **Authentication Issues**
   - Clear localStorage
   - Check token expiration
   - Verify backend auth endpoints

3. **Build Errors**
   - Check TypeScript errors
   - Verify all dependencies installed
   - Clear `.next` folder

### Debug Mode

Enable debug logging by setting:
```env
NODE_ENV=development
DEBUG=true
```

## 🤝 Contributing

### Development Guidelines

1. **Code Style**: Follow existing patterns
2. **TypeScript**: Use strict typing
3. **Components**: Create reusable components
4. **Testing**: Write tests for new features
5. **Documentation**: Update README for changes

### Pull Request Process

1. Fork the repository
2. Create feature branch
3. Make changes with tests
4. Submit pull request
5. Code review and merge

## 📚 Additional Resources

- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [shadcn/ui Documentation](https://ui.shadcn.com/)
- [React Hook Form](https://react-hook-form.com/)
- [Zod Validation](https://zod.dev/)

## 📄 License

This project is licensed under the ISC License.

---

**Note**: This frontend is designed to work with the StackTales backend API. Ensure the backend is running and properly configured before testing the frontend.
