import { useState } from "react"; import { motion } from "framer-motion"; import { Button } from "@/components/ui/button"; import { Card, CardContent } from "@/components/ui/card"; import { Rocket, Zap, Globe } from "lucide-react";

export default function PancaFlash() { const [copied, setCopied] = useState(false);

const handleCopy = () => { navigator.clipboard.writeText("YOUR_CONTRACT_ADDRESS_HERE"); setCopied(true); setTimeout(() => setCopied(false), 2000); };

return ( <div className="min-h-screen bg-gradient-to-b from-black via-gray-900 to-black text-white"> {/* Hero Section */} <section className="flex flex-col items-center justify-center text-center py-20 px-4"> <motion.h1 initial={{ opacity: 0, y: -20 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.8 }} className="text-5xl font-extrabold mb-4 bg-gradient-to-r from-yellow-400 to-red-500 bg-clip-text text-transparent" > Panca Flash ⚡ </motion.h1> <p className="text-lg max-w-2xl mb-6"> The lightning-fast meme coin on Solana. Built for speed, community, and unstoppable energy. </p> <div className="flex gap-4"> <Button
size="lg"
className="bg-yellow-500 hover:bg-yellow-600 rounded-2xl px-6"
> Buy on Pump.fun </Button> <Button
size="lg"
variant="outline"
className="rounded-2xl px-6"
onClick={handleCopy}
> {copied ? "Copied!" : "Copy Contract"} </Button> </div> </section>

{/* Features Section */}
  <section className="grid md:grid-cols-3 gap-6 px-6 md:px-20 py-16">
    <Card className="bg-gray-900 border-gray-800 shadow-lg">
      <CardContent className="flex flex-col items-center text-center p-6">
        <Rocket className="w-12 h-12 text-yellow-400 mb-4" />
        <h3 className="text-xl font-bold mb-2">Lightning Speed</h3>
        <p>Powered by Solana, transactions are instant and ultra-cheap.</p>
      </CardContent>
    </Card>
    <Card className="bg-gray-900 border-gray-800 shadow-lg">
      <CardContent className="flex flex-col items-center text-center p-6">
        <Zap className="w-12 h-12 text-red-400 mb-4" />
        <h3 className="text-xl font-bold mb-2">Meme Power</h3>
        <p>A community-driven token fueled by fun, hype, and culture.</p>
      </CardContent>
    </Card>
    <Card className="bg-gray-900 border-gray-800 shadow-lg">
      <CardContent className="flex flex-col items-center text-center p-6">
        <Globe className="w-12 h-12 text-green-400 mb-4" />
        <h3 className="text-xl font-bold mb-2">Global Community</h3>
        <p>Join the flash mob of believers making PANCA unstoppable.</p>
      </CardContent>
    </Card>
  </section>

  {/* Footer */}
  <footer className="text-center py-10 border-t border-gray-800 text-gray-400">
    <p>
      © {new Date().getFullYear()} Panca Flash. Built with ⚡ on Solana.
    </p>
  </footer>
</div>

); }

