import React, { useState, useEffect } from "react"; import { ethers } from "ethers";

export default function ShmuckleCoinPage() { const [walletAddress, setWalletAddress] = useState("");

const connectWallet = async () => { if (window.ethereum) { try { const accounts = await window.ethereum.request({ method: "eth_requestAccounts" }); setWalletAddress(accounts[0]); } catch (err) { console.error("Wallet connection failed", err); } } else { alert("Please install MetaMask to use this feature"); } };

return ( <div className="bg-black text-white min-h-screen font-sans"> <header className="bg-zinc-900 text-center p-6"> <h1 className="text-4xl font-bold text-green-400">Shmuckle Coin ($SML)</h1> <div className="mt-4 space-x-4"> <a className="bg-green-400 text-black px-4 py-2 rounded-xl" href="#buy">Buy Now</a> <a className="bg-green-400 text-black px-4 py-2 rounded-xl" href="https://twitter.com/ShmuckleCoin">Twitter</a> <a className="bg-green-400 text-black px-4 py-2 rounded-xl" href="https://t.me/ShmuckleCoin">Telegram</a> <button
onClick={connectWallet}
className="bg-green-400 text-black px-4 py-2 rounded-xl"
> {walletAddress ? Connected: ${walletAddress.slice(0, 6)}...${walletAddress.slice(-4)} : "Connect Wallet"} </button> </div> </header>

<main className="max-w-3xl mx-auto p-6">
    <section className="my-10">
      <h2 className="text-2xl text-green-400 font-bold">Welcome to $SML</h2>
      <p className="mt-2">The most useless token on the blockchain. No roadmap. No promises. Just pump.</p>
    </section>

    <section className="my-10">
      <h2 className="text-2xl text-green-400 font-bold">About $SML</h2>
      <p className="mt-2">$SML is a meme coin with zero fundamentals and 100% energy. Built for laughs, chaos, and potentially generational delusion.</p>
      <ul className="list-disc ml-6 mt-2">
        <li>420M Total Supply</li>
        <li>LP Burned</li>
        <li>Contract Renounced</li>
        <li>Degen-Powered</li>
      </ul>
    </section>

    <section className="my-10">
      <h2 className="text-2xl text-green-400 font-bold">Tokenomics</h2>
      <ul className="list-disc ml-6 mt-2">
        <li><strong>Supply:</strong> 420,000,000 $SML</li>
        <li><strong>Tax:</strong> 0/0</li>
        <li><strong>Utility:</strong> None</li>
        <li><strong>Mission:</strong> Confuse your financial advisor</li>
      </ul>
    </section>

    <section className="my-10" id="buy">
      <h2 className="text-2xl text-green-400 font-bold">How to Buy</h2>
      <ol className="list-decimal ml-6 mt-2">
        <li>Get ETH</li>
        <li>Go to Uniswap</li>
        <li>Paste our contract: <code>0x...SML</code></li>
        <li>Swap and pray</li>
        <li>Join Telegram and become a legend</li>
      </ol>
    </section>

    <section className="my-10">
      <h2 className="text-2xl text-green-400 font-bold">Meme Gallery</h2>
      <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4 mt-4">
        <img src="/images/meme1.png" alt="Meme 1" className="rounded-xl" />
        <img src="/images/meme2.png" alt="Meme 2" className="rounded-xl" />
        <img src="/images/meme3.png" alt="Meme 3" className="rounded-xl" />
      </div>
    </section>

    <section className="my-10">
      <h2 className="text-2xl text-green-400 font-bold">Community Links</h2>
      <ul className="list-disc ml-6 mt-2">
        <li><a className="text-green-400" href="https://t.me/ShmuckleCoin">Telegram</a></li>
        <li><a className="text-green-400" href="https://twitter.com/ShmuckleCoin">Twitter</a></li>
        <li><a className="text-green-400" href="https://www.dextools.io/">DexTools Chart</a></li>
        <li><a className="text-green-400" href="#">CoinGecko (soon™)</a></li>
      </ul>
    </section>
  </main>

  <footer className="bg-zinc-900 text-center p-4">
    <p>&copy; 2025 Shmuckle Coin. Powered by pure degen energy.</p>
  </footer>
</div>

); }

