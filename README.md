# ShopHub - Modern E-Commerce Store

A complete, modern e-commerce website built with Nuxt 3, Vue.js, and Tailwind CSS.

## 🚀 Features

- **Modern UI/UX**: Clean, responsive design with Tailwind CSS
- **Product Catalog**: Browse 12 pre-loaded products across 4 categories
- **Shopping Cart**: Full-featured cart with sidebar, persistence, and quantity management
- **Product Search**: Real-time search and category filtering
- **Product Details**: Detailed product pages with related items
- **Checkout Flow**: Complete checkout form with order summary
- **Responsive Design**: Mobile-first approach, works on all devices
- **State Management**: Pinia stores for cart and products
- **Local Storage**: Cart persists between sessions

## 📦 Tech Stack

- **Framework**: Nuxt 3
- **UI Library**: Vue 3 (Composition API)
- **Styling**: Tailwind CSS
- **State Management**: Pinia
- **Routing**: Vue Router (built into Nuxt)

## 🛠️ Installation

1. **Extract the project** (if you downloaded as archive)
   ```bash
   unzip ecommerce-store.zip
   # or
   tar -xzf ecommerce-store.tar.gz
   ```

2. **Navigate to the project directory**
   ```bash
   cd ecommerce-store-complete
   ```

3. **Install dependencies**
   ```bash
   npm install
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

5. **Open your browser**
   
   Navigate to `http://localhost:3000`

## 📝 Available Scripts

```bash
# Development server
npm run dev

# Build for production
npm run build

# Generate static site
npm run generate

# Preview production build
npm run preview
```

## 📁 Project Structure

```
ecommerce-store-complete/
├── assets/
│   └── css/
│       └── main.css          # Global styles and Tailwind
├── components/
│   ├── Header.vue            # Navigation header
│   ├── Footer.vue            # Site footer
│   ├── ProductCard.vue       # Product display card
│   └── CartSidebar.vue       # Shopping cart sidebar
├── pages/
│   ├── index.vue             # Home page
│   ├── checkout.vue          # Checkout page
│   └── products/
│       ├── index.vue         # Products listing
│       └── [id].vue          # Product detail page
├── stores/
│   ├── cart.js               # Shopping cart store
│   └── products.js           # Products store
├── app.vue                   # Root component
├── nuxt.config.ts            # Nuxt configuration
├── tailwind.config.js        # Tailwind configuration
└── package.json              # Project dependencies
```

## 🎨 Customization

### Adding New Products

Edit `stores/products.js` and add new product objects to the `products` array:

```javascript
{
  id: 13,
  name: 'Your Product',
  description: 'Product description',
  price: 99.99,
  originalPrice: 129.99,  // Optional
  discount: 23,           // Optional (percentage)
  image: 'https://your-image-url.com/image.jpg',
  category: 'Electronics',
  rating: 5,
  stock: 10
}
```

### Changing Colors

Edit `tailwind.config.js` to customize the color scheme:

```javascript
theme: {
  extend: {
    colors: {
      primary: {
        // Your custom colors
      }
    }
  }
}
```

### Modifying Layouts

- **Header**: Edit `components/Header.vue`
- **Footer**: Edit `components/Footer.vue`
- **Product Cards**: Edit `components/ProductCard.vue`

## 🌟 Key Features Explained

### Shopping Cart
- Add/remove items
- Update quantities
- Persistent storage (localStorage)
- Slide-out sidebar
- Real-time total calculation

### Product Catalog
- Category filtering
- Real-time search
- Responsive grid layout
- Stock management
- Discount badges

### Checkout
- Complete form validation
- Order summary
- Tax and shipping calculation
- Responsive design

## 🚀 Deployment

### Vercel (Recommended)
```bash
npm run build
```
Then deploy the `.output` directory to Vercel.

### Netlify
```bash
npm run generate
```
Deploy the `.output/public` directory to Netlify.

### Traditional Hosting
```bash
npm run generate
```
Upload the contents of `.output/public` to your hosting provider.

## 📱 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

## 🤝 Contributing

This is a starter template. Feel free to:
- Add new features
- Customize the design
- Integrate with a backend API
- Add user authentication
- Implement payment processing

## 📄 License

This project is provided as-is for educational and commercial use.

## 🔗 Resources

- [Nuxt 3 Documentation](https://nuxt.com/docs)
- [Vue 3 Documentation](https://vuejs.org/)
- [Tailwind CSS Documentation](https://tailwindcss.com/)
- [Pinia Documentation](https://pinia.vuejs.org/)

## 💡 Next Steps

1. **Add Backend Integration**: Connect to a real API or database
2. **User Authentication**: Implement login/signup functionality
3. **Payment Processing**: Integrate Stripe or PayPal
4. **Product Reviews**: Add user review system
5. **Order History**: Track customer orders
6. **Admin Panel**: Manage products and orders
7. **Email Notifications**: Send order confirmations
8. **Advanced Search**: Add filters, sorting, price ranges

## 🐛 Troubleshooting

### Port Already in Use
```bash
PORT=3001 npm run dev
```

### Dependencies Issues
```bash
rm -rf node_modules package-lock.json
npm install
```

### Build Errors
Ensure you're using Node.js 18+ and npm 9+:
```bash
node --version
npm --version
```

## 📞 Support

For questions or issues, please refer to the Nuxt 3 documentation or create an issue in your repository.

---

**Happy Coding! 🎉**
