# Development Guide

This guide provides information for developers working on the Real State project.

## Project Architecture

### Directory Structure

```
src/
├── Component/              # Reusable UI components
│   ├── Accordion/         # Expandable accordion sections
│   ├── Companies/         # Partner companies showcase
│   ├── Extra/             # Additional sections
│   ├── Header/            # Header and navigation
│   └── Value/             # Value proposition display
├── Residencies/           # Property listing components
├── Utils/                 # Utility functions and helpers
├── App.js                 # Main application component
├── App.css                # Application styles
├── index.js               # React entry point
├── index.css              # Global styles
└── reportWebVitals.js     # Performance monitoring
```

## Component Hierarchy

```
App
├── Header
├── Extra
├── Companies
├── Residencies
└── Value
```

## Development Workflow

### 1. Starting Development

```bash
npm install
npm start
```

The application will start at `http://localhost:3000` with hot-reload enabled.

### 2. Adding New Components

Create a new component folder under `src/Component/`:

```javascript
// src/Component/YourComponent/YourComponent.js
import React from 'react';
import './YourComponent.css';

const YourComponent = () => {
  return (
    <div className="your-component">
      {/* Your JSX here */}
    </div>
  );
};

export default YourComponent;
```

### 3. Creating Utilities

Add utility functions to `src/Utils/`:

```javascript
// src/Utils/helpers.js
export const formatPrice = (price) => {
  return new Intl.NumberFormat('en-US', {
    style: 'currency',
    currency: 'USD'
  }).format(price);
};
```

### 4. Styling Components

Use CSS files alongside components:

```css
/* src/Component/YourComponent/YourComponent.css */
.your-component {
  padding: 2rem;
  border-radius: 8px;
}
```

## Available Dependencies

### Core Libraries
- **react**: UI library
- **react-dom**: DOM rendering
- **react-scripts**: Build and development tools

### UI/Animation
- **swiper**: Touch slider carousel
- **react-icons**: Icon library (FaIcon, BiIcon, etc.)
- **react-countup**: Number animation effects

### Testing
- **@testing-library/react**: React component testing
- **@testing-library/jest-dom**: Jest DOM matchers
- **@testing-library/user-event**: User interaction simulation

## Building for Production

### Production Build

```bash
npm run build
```

This creates an optimized build in the `build/` directory:
- Minified JavaScript and CSS
- Optimized images and assets
- Source maps for debugging

### Performance Optimization Tips

1. **Code Splitting**: Use React.lazy() and Suspense for route-based splitting
2. **Image Optimization**: Use appropriate formats and sizes
3. **Bundle Analysis**: Analyze bundle size with `npm run build`
4. **Lazy Loading**: Implement lazy loading for off-screen content

## Testing

### Running Tests

```bash
npm test
```

### Writing Tests

Create test files with `.test.js` extension:

```javascript
// src/Component/Header/Header.test.js
import { render, screen } from '@testing-library/react';
import Header from './Header';

test('renders header component', () => {
  render(<Header />);
  expect(screen.getByRole('header')).toBeInTheDocument();
});
```

## Debugging

### Browser DevTools
1. React Developer Tools extension
2. Redux DevTools (if using Redux)
3. Network tab for API calls
4. Console for error logs

### VS Code Debugging
1. Install Debugger for Chrome
2. Create debug configuration in `.vscode/launch.json`
3. Set breakpoints and debug

## Git Workflow

```bash
# Create feature branch
git checkout -b feature/your-feature

# Make changes and commit
git commit -m "Add your feature description"

# Push to remote
git push origin feature/your-feature

# Create Pull Request on GitHub
```

## Environment Variables

Create `.env.local` file in root directory:

```
REACT_APP_API_URL=http://localhost:3001
REACT_APP_ENV=development
```

Access in code:
```javascript
const apiUrl = process.env.REACT_APP_API_URL;
```

## Performance Monitoring

The project includes Web Vitals monitoring:

```javascript
import reportWebVitals from './reportWebVitals';

reportWebVitals(console.log);
```

This tracks:
- CLS (Cumulative Layout Shift)
- FID (First Input Delay)
- FCP (First Contentful Paint)
- LCP (Largest Contentful Paint)
- TTFB (Time to First Byte)

## Troubleshooting

### Port Already in Use
```bash
# Windows
netstat -ano | findstr :3000
taskkill /PID <PID> /F

# macOS/Linux
lsof -ti:3000 | xargs kill -9
```

### Clear Cache
```bash
# Delete node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
```

### Build Issues
```bash
# Clear npm cache
npm cache clean --force

# Reinstall dependencies
rm -rf node_modules
npm install
```

## Resources

- [React Documentation](https://react.dev)
- [Create React App Docs](https://create-react-app.dev)
- [Swiper Documentation](https://swiperjs.com)
- [React Icons](https://react-icons.github.io/react-icons/)

---

For more questions, please open an issue on GitHub.
