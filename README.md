import React from "react";
import { motion } from "framer-motion";
import { ShoppingBag, Mail, Menu } from "lucide-react";

export default function VoidLanding() {
  return (
    <div className="min-h-screen bg-gradient-to-b from-gray-50 via-gray-100 to-gray-200 text-gray-900 antialiased">
      {/* Header */}
      <header className="flex items-center justify-between px-6 py-5 md:py-6 lg:px-12 border-b border-gray-300 bg-white/60 backdrop-blur-md">
        <div className="flex items-center gap-4">
          <Logo />
          <span className="hidden md:inline-block font-medium tracking-wider">VOID</span>
        </div>

        <nav className="hidden md:flex gap-8 items-center text-sm font-medium">
          <a href="#about" className="hover:text-gray-700">About</a>
          <a href="#shop" className="hover:text-gray-700">Shop</a>
          <a href="#custom" className="hover:text-gray-700">Custom Prints</a>
          <a href="#contact" className="hover:text-gray-700">Contact</a>
          <button className="ml-2 inline-flex items-center gap-2 rounded-lg border px-3 py-1.5 text-sm bg-gradient-to-r from-gray-900 to-gray-700 text-white">
            <ShoppingBag size={16} /> Shop
          </button>
        </nav>

        <div className="md:hidden">
          <button aria-label="menu" className="p-2 rounded">
            <Menu size={20} />
          </button>
        </div>
      </header>

      {/* Hero */}
      <main className="px-6 lg:px-12">
        <section className="grid grid-cols-1 md:grid-cols-2 gap-8 items-center pt-12 pb-16">
          <div>
            <motion.h1
              initial={{ opacity: 0, y: 8 }}
              animate={{ opacity: 1, y: 0 }}
              transition={{ duration: 0.6 }}
              className="text-4xl md:text-5xl lg:text-6xl font-extrabold leading-tight bg-gradient-to-r from-gray-900 via-gray-800 to-gray-600 bg-clip-text text-transparent"
            >
              VOID — Minimal. Rare. Premium.
            </motion.h1>

            <p className="mt-6 max-w-xl text-gray-700">
              Street-ready premium T‑shirts with minimal aesthetic and museum-grade prints.
              Limited drops, clean cuts, and made for the Gen‑Z wardrobe.
            </p>

            <div className="mt-8 flex gap-4">
              <a
                href="#shop"
                className="inline-block rounded-lg border border-gray-400 px-5 py-3 text-sm font-semibold bg-white/70 backdrop-blur-sm hover:bg-white/90"
              >
                Shop Drops
              </a>

              <a
                href="#custom"
                className="inline-block rounded-lg bg-gradient-to-r from-gray-900 to-gray-700 text-white px-5 py-3 text-sm font-semibold hover:opacity-90"
              >
                Custom Prints
              </a>
            </div>

            <div className="mt-8 text-xs text-gray-600">
              <strong>Note:</strong> Free standard shipping on orders over ₹3500.
            </div>
          </div>

          <div className="flex items-center justify-center">
            <motion.div
              initial={{ scale: 0.98, opacity: 0 }}
              animate={{ scale: 1, opacity: 1 }}
              transition={{ duration: 0.6 }}
              className="w-72 h-88 md:w-96 md:h-104 rounded-2xl shadow-2xl border border-gray-300 p-8 flex flex-col items-center justify-center bg-white/70 backdrop-blur-md"
            >
              <div className="w-full h-full flex items-center justify-center">
                <div className="w-48 md:w-64 h-48 md:h-64 bg-gradient-to-br from-gray-100 to-gray-200 rounded-lg flex items-center justify-center">
                  <LogoLarge />
                </div>
              </div>
            </motion.div>
          </div>
        </section>

        {/* About */}
        <section id="about" className="py-12 border-t border-gray-300 bg-white/60 backdrop-blur-md rounded-xl px-6">
          <div className="max-w-4xl">
            <h2 className="text-2xl font-bold text-gray-900">Our Philosophy</h2>
            <p className="mt-4 text-gray-700">
              VOID creates premium T-shirts blending minimalism with bold storytelling.
              We source high GSM fabrics, use archival pigment inks, and run small drops to maintain rarity.
            </p>

            <div className="mt-8 grid grid-cols-1 sm:grid-cols-3 gap-6">
              <Feature title="Premium Materials" desc="320–380 GSM cotton, soft-hand finish." />
              <Feature title="Limited Drops" desc="Small-batch prints to keep exclusivity." />
              <Feature title="Sustainable" desc="Water-based inks and low-waste production." />
            </div>
          </div>
        </section>

        {/* Shop */}
        <section id="shop" className="py-12 border-t border-gray-300">
          <div className="max-w-5xl">
            <h2 className="text-2xl font-bold text-gray-900">Latest Drop</h2>
            <p className="mt-3 text-gray-700">Hand-numbered, limited to 75 pieces.</p>

            <div className="mt-8 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
              {new Array(3).fill(0).map((_, i) => (
                <ProductCard key={i} index={i + 1} />
              ))}
            </div>
          </div>
        </section>

        {/* Custom prints CTA */}
        <section id="custom" className="py-12 border-t border-gray-300 rounded-lg mt-8 bg-white/70 backdrop-blur-md">
          <div className="max-w-4xl p-8 rounded-lg">
            <h3 className="text-xl font-semibold text-gray-900">Custom & Collaborations</h3>
            <p className="mt-3 text-gray-700">Partner with VOID for one-off prints, brand collabs, and small runs.</p>
            <div className="mt-6">
              <a href="#contact" className="inline-flex items-center gap-2 rounded-lg border border-gray-400 px-4 py-2 bg-white/80 hover:bg-white">
                <Mail size={16} /> Get in touch
              </a>
            </div>
          </div>
        </section>

        {/* Contact */}
        <section id="contact" className="py-12 border-t border-gray-300">
          <div className="max-w-3xl">
            <h2 className="text-2xl font-bold text-gray-900">Contact</h2>
            <form className="mt-6 grid grid-cols-1 gap-4">
              <input
                className="border rounded-lg px-4 py-3 bg-gray-50"
                placeholder="Your name"
                aria-label="name"
              />
              <input
                className="border rounded-lg px-4 py-3 bg-gray-50"
                placeholder="Email"
                aria-label="email"
              />
              <textarea className="border rounded-lg px-4 py-3 h-28 bg-gray-50" placeholder="Message" />
              <div className="flex items-center gap-3">
                <button className="rounded-lg bg-gradient-to-r from-gray-900 to-gray-700 text-white px-4 py-2">Send</button>
                <span className="text-xs text-gray-500">We'll reply within 2 business days.</span>
              </div>
            </form>
          </div>
        </section>

        <footer className="mt-16 py-8 border-t border-gray-300 bg-white/60 backdrop-blur-md">
          <div className="flex flex-col md:flex-row items-center justify-between gap-6">
            <div className="flex items-center gap-3">
              <Logo />
              <span className="text-sm">© {new Date().getFullYear()} VOID</span>
            </div>

            <div className="text-sm text-gray-500">Designed with love for minimal streetwear.</div>
          </div>
        </footer>
      </main>
    </div>
  );
}

function Logo() {
  return (
    <svg width="40" height="28" viewBox="0 0 120 40" fill="none" xmlns="http://www.w3.org/2000/svg">
      <rect width="120" height="40" rx="6" fill="#000" />
      <text x="50%" y="58%" textAnchor="middle" fill="#fff" fontFamily="Inter, system-ui" fontWeight="700" fontSize="16">VOID</text>
    </svg>
  );
}

function LogoLarge() {
  return (
    <svg width="160" height="160" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
      <circle cx="100" cy="100" r="96" stroke="#000" strokeWidth="6" fill="white" />
      <text x="50%" y="55%" textAnchor="middle" fill="#000" fontFamily="Inter, system-ui" fontWeight="800" fontSize="48">VOID</text>
    </svg>
  );
}

function Feature({ title, desc }) {
  return (
    <div className="p-4 bg-white/80 border border-gray-300 rounded-lg shadow-sm">
      <h4 className="font-semibold text-gray-900">{title}</h4>
      <p className="mt-2 text-sm text-gray-700">{desc}</p>
    </div>
  );
}

function ProductCard({ index = 1 }) {
  return (
    <div className="border border-gray-300 rounded-2xl p-4 flex flex-col gap-4 bg-white/80 shadow-sm">
      <div className="w-full h-52 rounded-lg bg-gradient-to-br from-gray-100 to-gray-200 flex items-center justify-center">
        <div className="text-6xl font-black tracking-tight text-gray-900">V</div>
      </div>
      <div className="flex items-center justify-between">
        <div>
          <div className="font-semibold text-gray-900">VOID Tee — Drop {index}</div>
          <div className="text-xs text-gray-500">Limited • Hand-numbered</div>
        </div>
        <div className="text-sm font-semibold text-gray-900">₹2499</div>
      </div>
      <div className="flex items-center gap-2">
        <button className="flex-1 rounded-lg border border-gray-400 px-4 py-2 text-sm bg-white/80 hover:bg-white">Buy</button>
        <button className="rounded-lg border border-gray-400 px-3 py-2 text-sm bg-white/80 hover:bg-white">View</button>
      </div>
    </div>
  );
}
