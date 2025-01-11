# Setting Up a Next.js Project with TypeScript and Tailwind CSS

This documentation provides step-by-step instructions for setting up a Next.js project with TypeScript and Tailwind CSS, including troubleshooting and configuration.

---

## 1. Install Node.js

### Download and Install:
1. Visit the [Node.js official website](https://nodejs.org/).
2. Download the **LTS version** (recommended for most users).
3. Run the installer and follow these steps:
   - Accept the license agreement.
   - Choose the default installation path (e.g., `C:\Program Files\nodejs`).
   - Ensure you check the box to **Add Node.js to PATH**.
   - Install any additional tools if prompted.

### Verify Installation:
After installation, open a terminal and run:
```bash
node -v
npm -v
```
You should see the installed versions of Node.js and npm.

---

## 2. Create a New Next.js Project

### Using npx:
Run the following command in your desired directory:
```bash
npx create-next-app@latest --typescript project-name
```
Replace `project-name` with the name of your project. For example:
```bash
npx create-next-app@latest --typescript digitaley-drive-dashboard
```

### Navigate to the Project Directory:
```bash
cd digitaley-drive-dashboard
```

---

## 3. Install Tailwind CSS

### Add Tailwind Dependencies:
Run the following command to install Tailwind CSS:
```bash
npm install -D tailwindcss postcss autoprefixer
```

### Initialize Tailwind Configuration:
Generate the `tailwind.config.js` and `postcss.config.js` files:
```bash
npx tailwindcss init -p
```

### Configure Content Paths:
Update `tailwind.config.js` to include paths for your project files:
```javascript
module.exports = {
  content: [
    "./app/**/*.{js,ts,jsx,tsx}",
    "./components/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

### Add Tailwind Directives to CSS:
Open `globals.css` (usually in `app/globals.css`) and add:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

---

## 4. Start the Development Server

### Run the Dev Server:
In the project directory, run:
```bash
npm run dev
```
This starts the development server, usually available at `http://localhost:3000/`.

### Troubleshooting:
- If `npm` is not recognized, ensure Node.js is properly installed and added to PATH.
- Verify the Node.js installation path:
  ```bash
  where node
  where npm
  ```

---

## 5. Additional Configuration

### Add a Favicon:
1. Convert your desired image to a favicon using tools like [Favicon Generator](https://favicon.io/).
2. Replace the default favicon in the `public` folder (e.g., `favicon.ico`).

### Update Metadata:
Edit `app/layout.tsx` to update the title and description:
```typescript
export const metadata = {
  title: "Digitaley Drive Dashboard",
  description: "Community dashboard for Digitaley Drive.",
};
```

### Add Libraries (Optional):
Install additional dependencies such as `shadcn/ui` for pre-built components:
```bash
npm install shadcn/ui
```

---

## 6. Folder Structure
Ensure your project folders are well-organized:
```
project-name/
├── app/
│   ├── favicon.ico
│   ├── globals.css
│   ├── layout.tsx
│   └── page.tsx
├── components/
├── public/
├── tailwind.config.js
├── package.json
└── ...
```

---

## 7. Development Workflow

### Branching Strategy:
- **Development Branch:** Never push directly to the main branch.
- Create a new branch for each task:
  ```bash
  git checkout -b feature-branch-name
  ```

### Commit and Push:
- After completing changes:
  ```bash
  git add .
  git commit -m "Your commit message"
  git push origin feature-branch-name
  ```

### Submit a Pull Request:
- Open a pull request to merge into the `development` branch.

---

## 8. Resources
- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [Node.js Documentation](https://nodejs.org/en/docs)

---

Following these steps ensures a clean and efficient setup for your Next.js project with TypeScript and Tailwind CSS.

