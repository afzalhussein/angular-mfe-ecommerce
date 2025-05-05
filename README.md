# angular-mfe-ecommerce-
Angular Micro Frontends (MFE) E-Commerce Example

## Repository Structure
```
/angular-mfe-ecommerce
│
├── /shell/                   # Host application (Angular 16)
│   ├── webpack.config.js     # Module Federation setup
│   └── src/app/routes        # Lazy-loaded MFE routes
│
├── /product-catalog/         # Product MFE (Angular 16)
│   ├── webpack.config.js     # Exposes ProductModule
│   └── src/app/product       # Product listing components
│
├── /shopping-cart/           # Cart MFE (Angular 16)
│   ├── webpack.config.js     # Exposes CartModule
│   └── src/app/cart          # Cart state management
│
├── /user-dashboard/          # User MFE (Angular 15)
│   └── webpack.config.js     # Version-specific shared deps
│
├── /recommendations/         # React MFE (React 18)
│   └── src/Recommendations.js # Exposed as Web Component
│
├── /shared-lib/              # Shared services (Cart/EventBus)
│   └── src/lib               # Published as npm package
│
└── README.md                 # Setup + deployment guide
```

## Key Features Implemented
1. **Module Federation Configuration**

   - Dynamic remote loading (productCatalog@http://localhost:4201/remoteEntry.js)

   - Shared dependency management (@angular/core, rxjs)

2. **Cross-MFE Communication**

   - Event bus for cart updates

   - Shared CartService in shared-lib

3. **Mixed Framework Integration**

   - Angular host + React remote (via Web Components)

4. **Performance Optimizations**

   - Lazy loading (loadChildren)

   - Dependency sharing (no duplicate @angular/core)

5. **Testing**

   - Cypress E2E tests for cross-MFE workflows

   - Jest unit tests in each MFE
  
## How to Run the Project

```bash
# Clone the repo
git clone https://github.com/your-username/angular-mfe-ecommerce.git
cd angular-mfe-ecommerce

# Install dependencies
npm run install:all

# Start all MFEs in parallel
npm run start:all

# Open shell app at http://localhost:4200
```
## What You'll Learn
   ✅ Module Federation setup in Angular

   ✅ State sharing between independent MFEs

   ✅ Legacy Angular (v15) + modern Angular (v16) integration

   ✅ React + Angular coexistence strategies

   ✅ CI/CD pipelines for independent deployments

## Next Steps
1. Explore the Code:

   - Check shell/webpack.config.js for host configuration

   - See product-catalog/src/app/product.module.ts for exposed module

2. Try These Modifications:

   - Add a new MFE (e.g., PaymentModule)

   - Implement NgRx for shared state

   - Upgrade user-dashboard to Angular 16
  
