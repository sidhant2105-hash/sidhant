# sidhant
// This is a SIMPLE, CLEAN starter setup for your website
// Stack: Next.js (App Router) + Tailwind CSS
// You can push this to GitHub and deploy on Vercel

// ================================
// app/page.tsx (MAIN PAGE)
// ================================
import { Header } from "@/components/Header";
import { Hero } from "@/components/Hero";
import { ProductGrid } from "@/components/ProductGrid";
import { Footer } from "@/components/Footer";

export default function Home() {
  return (
    <div className="min-h-screen bg-zinc-950 text-zinc-100 font-sans">
      <Header />
      <main>
        <Hero />
        <ProductGrid />
      </main>
      <Footer />
    </div>
  );
}

// ================================
// components/Header.tsx
// ================================
export function Header() {
  return (
    <header className="flex items-center justify-between px-6 py-4 border-b border-zinc-800">
      <h1 className="text-xl font-bold">GULLY ROOTS</h1>
      <nav className="space-x-6 text-sm">
        <a href="#" className="hover:text-red-500">Home</a>
        <a href="#" className="hover:text-red-500">Shop</a>
        <a href="#" className="hover:text-red-500">Contact</a>
      </nav>
    </header>
  );
}

// ================================
// components/Hero.tsx
// ================================
export function Hero() {
  return (
    <section className="px-6 py-24 text-center">
      <h2 className="text-4xl md:text-6xl font-extrabold">
        Streetwear From The Roots
      </h2>
      <p className="mt-4 text-zinc-400 max-w-xl mx-auto">
        Built for the streets. Designed for comfort. Worn with pride.
      </p>
      <button className="mt-8 bg-red-500 hover:bg-red-600 px-8 py-3 rounded-md font-semibold">
        Shop Now
      </button>
    </section>
  );
}

// ================================
// components/ProductGrid.tsx
// ================================
const products = [
  { id: 1, name: "Black Hoodie", price: "₹1,499" },
  { id: 2, name: "Oversized Tee", price: "₹899" },
  { id: 3, name: "Street Cap", price: "₹599" },
];

export function ProductGrid() {
  return (
    <section className="px-6 py-16">
      <h3 className="text-2xl font-bold mb-8 text-center">Featured Drops</h3>
      <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
        {products.map((product) => (
          <div
            key={product.id}
            className="border border-zinc-800 rounded-lg p-4 hover:border-red-500 transition"
          >
            <div className="h-48 bg-zinc-800 rounded mb-4" />
            <h4 className="font-semibold">{product.name}</h4>
            <p className="text-zinc-400">{product.price}</p>
          </div>
        ))}
      </div>
    </section>
  );
}

// ================================
// components/Footer.tsx
// ================================
export function Footer() {
  return (
    <footer className="px-6 py-6 border-t border-zinc-800 text-center text-sm text-zinc-500">
      © {new Date().getFullYear()} Gully Roots. All rights reserved.
    </footer>
  );
}
