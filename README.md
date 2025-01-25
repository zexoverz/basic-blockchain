## Advanced Blockchain: How Actually Blockchain Works By Zexo

**"Katanya sih, 'Gak ada yang paham Bitcoin, tapi gapapa'? Yuk Kita Bongkar!**  

Pernah dengar orang bilang, *"Gak ada yang paham Bitcoin, tapi ya gapapa lah"*? **BULLSHIT!**  
Sebenarnya, emang banyak yang gak paham, tapi lucunya… *orang tetep pake aja* 😅. *Sama kayak lo pake Wi-Fi tiap hari tapi gak tau cara kerja router!*  

Nah, masalahnya… **blockchain itu bukan cuma urusan koding doang!** Ini campur aduk: *ekonomi, konsep keuangan baru, sampe politik*. Makanya, otak kita sering **ERROR 404** pas mau ngerti. *Bikin pusing tujuh keliling kan?*  

Sebelom nulis ini, gw udah *"nongkrong virtual"* sama ahli-ahli kripto, dari tukang airdrop sampe developer blockchain. Eh, tau gak? **Jawabannya beda-beda!** 🥲  
- Ada yang bilang blockchain itu kayak Google Sheets  
- Ada yang bilang mirip *database alien*  
- Bahkan ada yang nyebut "blockchain itu cuma hype doang" (wtf?!)  

Tapi setelah gw telusuri… **blockchain emang terlihat mistis kayak drakor plot twist!** Tapi tenang—gw bakal jadi *"Dumbledore"* lo buat jelasin ini semua pake bahasa manusia.  

*Intinya: Gak usah takut!* Blockchain itu kayak resep martabak—kelihatan ribet, tapi kalo udah tau caranya, *lu bisa jualan di depan rumah*. **Santai aja, gw bakal jelasin pake diagram keren!**  


---

### **1. Membongkar Mitos Blockchain**  
#### **Mitos 1: "Blockchain = Bitcoin"**  
- **Fakta**: Bitcoin hanyalah "menu pertama" yang menggunakan blockchain. Blockchain sendiri adalah **infrastruktur dapurnya**.  
- **Contoh**: Seperti HTTP untuk web, blockchain adalah protokol yang bisa digunakan untuk banyak aplikasi (keuangan, logistik, dll).  

#### **Mitos 2: "Blockchain Hanya untuk Keuangan"**  
- **Fakta**: Blockchain bisa digunakan untuk:  
  - **Supply Chain**: Lacak asal usul bahan makanan.  
  - **Kesehatan**: Rekam medis pasien yang aman.  
  - **Voting Sistem**: Pemilu anti-kecurangan.  

#### **Mitos 3: "Hanya Ada Satu Blockchain"**  
- **Jenis Blockchain**:  
  1. **Publik** (Ethereum): Terbuka untuk semua.  
  2. **Privat** (Hyperledger): Hanya untuk anggota tertentu.  
  3. **Hybrid** (IBM Food Trust): Gabungan keduanya.  

### Anatomi Blockchain
Blockchain adalah rantai blok digital yang berfungsi sebagai buku besar terdistribusi. Setiap blok mengandung:

`Data` Transaksi: Catatan pengiriman aset digital (contoh: "Alice mengirim 1 BTC ke Bob").

`Hash`: Seperti sidik jari unik yang dihasilkan dari algoritma kriptografi (SHA-256 di Bitcoin). Contoh: a3f4...8b9c.

`Hash Blok Sebelumnya`: Menghubungkan blok saat ini ke blok sebelumnya, membentuk rantai.

`Analogi`: Bayangkan buku diary yang setiap halamannya (blok) memiliki:

- Catatan transaksi hari ini

- Stempel khusus (hash)

- Referensi ke stempel halaman sebelumnya.

---

### **2. Arsitektur Blockchain: Dari Transaksi Hingga Block**  
#### **Langkah demi Langkah**:  
1. **Transaksi Dibuat**: Anda mengirim 1 ETH ke teman.  
2. **Validasi oleh Node**:  
   - Node memeriksa saldo dan tanda tangan digital.  
   - Jika valid, transaksi masuk ke **mempool** (antrian transaksi).  
3. **Mining/Penambangan**:  
   - Miner bersaing memecahkan teka-teki kriptografi (cari **nonce**).  
   - **Nonce** adalah angka acak yang membuat hash block memenuhi syarat (misal: hash dimulai dengan 0000).  
4. **Block Terbentuk**:  
   - Transaksi dikelompokkan dalam block.  
   - Block ditambahkan ke rantai setelah konsensus tercapai.  

Struktur Block dan Transaksi (Visualisasi)**  
#### **Contoh Block #123456**  
| Field           | Value (Contoh)                          |  
|-----------------|-----------------------------------------|  
| **Block Number**| 123456                                  |  
| **Previous Hash**| 0x0000a1b2c3d4e5f6...7890abcedf1234    |  
| **Merkle Root** | 0x5f4d3c2b1a098765...4321fedcba9876    |  
| **Timestamp**   | 2023-08-15 14:30:00 UTC                |  
| **Nonce**       | 1897246                                |  
| **Transactions**| 3 transaksi (lihat contoh di bawah)    |  

#### **Contoh Transaksi #1 dalam Block**  
```json
{
  "from": "0xAb58...0901",
  "to": "0xCd34...5678",
  "amount": 1.5,
  "gas": 21000,
  "gasPrice": 40 Gwei,
  "hash": "0x1a2b3c4d5e6f...7890abcdef",
  "nonce": 42,
  "signature": "0x3045...0221"
}
```

![Proses Mining](https://miro.medium.com/v2/resize:fit:1400/1*4sjc5S7vY5JhqH7V6E6w7A.png)  
*Illustrasi Proses Mining: Mencari Nonce seperti Mencari Jarum di Tumpukan Jerami*  

---

### **3. Node: Koki di Dapur Blockchain**  
#### **Peran Node**:  
- **Full Node**: Menyimpan seluruh riwayat blockchain (1 TB+).  
- **Light Node**: Hanya menyimpan header block (hemat bandwidth).  
- **Mining Node**: Bertugas menambang block baru.  

#### **Cara Menjalankan Node**:  
1. Unduh client (e.g., Geth untuk Ethereum).  
2. Sinkronisasi data (butuh waktu *hari* untuk blockchain besar).  
3. Terus online untuk validasi transaksi.  

**Contoh Biaya**:  
- Hard disk: 2 TB.  
- RAM: 16 GB.  
- Koneksi internet: 100 Mbps.  

#### Proses Validasi Transaksi (Step-by-Step)
1. **Verifikasi Signature**  
   - Input: `signature`, `public key`, `transaction hash`  
   - Algoritma: ECDSA (Elliptic Curve Digital Signature Algorithm)  
   - Proses:  
     ```python
     # Contoh pseudocode
     public_key = ecdsa_recover(signature, transaction_hash)
     assert public_key == sender_address
     ```

2. **Cek Nonce**  
   - Setiap akun memiliki counter nonce yang increment untuk tiap transaksi  
   - Contoh: Nonce transaksi harus = 42 jika transaksi sebelumnya menggunakan nonce 41  

3. **Validasi State**  
   - Node memeriksa saldo pengirim di database state terbaru  
   - Jika pengirim punya 5 ETH dan mengirim 3 ETH → valid  
   - Jika mengirim 6 ETH → transaksi ditolak  

4. **Broadcast ke Jaringan**  
   - Transaksi valid dikirim ke node tetangga melalui protokol gossip  
   - Waktu propagasi: <2 detik untuk 95% node (pada Ethereum)  

5. **Dimasukkan ke Memory Pool**  
   - Transaksi menunggu di mempool sampai miner/validator memasukkannya ke block  

---

### **4. Smart Contract: Resep Masak Otomatis**  
**Apa Itu Smart Contract?**  
Smart contract adalah **program komputer** yang berjalan di blockchain dan menjalankan perintah secara otomatis ketika syarat tertentu terpenuhi. Bayangkan ini seperti **mesin penjual otomatis**:  
- Masukkan uang (penuhi syarat) → Dapatkan minuman (aksi dieksekusi).  
- Tanpa perlu kasir atau pihak ketiga!  
---

#### **Cara Kerja Smart Contract**  
1. **Ditulis dalam Kode**  
   - Developer membuat aturan pakai bahasa pemrograman (contoh: Solidity di Ethereum).  
   - Contoh aturan: *"Jika Transfer diterima, kirim NFT ke pembeli."*  

2. **Di-Deploy ke Blockchain**  
   - Kode dikirim ke jaringan blockchain (misal: Ethereum) dan disimpan di semua node.  

3. **Eksekusi Otomatis**  
   - Ketika kondisi terpenuhi (misal: pembayaran diterima), smart contract langsung bekerja.  
   - Tidak bisa diubah/dihentikan setelah di-deploy!  

---

#### **Contoh Nyata Smart Contract**  
**Kasus: Jual Beli Rumah* 
1. Pembeli setor uang ke escrow di smart contract.  
2. Smart contract verifikasi:  
   - Jika dokumen kepemilikan valid → Kirim uang ke penjual & serahkan sertifikat.  
   - Jika gagal → Kembalikan uang ke pembeli.  
3. **Tidak perlu notaris atau bank!**  

---

#### **Keunggulan Smart Contract**  
| **Fitur**         | **Manfaat**                                  |  
|--------------------|----------------------------------------------|  
| **Tanpa Perantara** | Tidak butuh bank, notaris, atau pihak ketiga |  
| **Transparan**     | Kode terbuka, bisa diverifikasi publik       |  
| **Aman**           | Data di blockchain tidak bisa di-hack        |  
| **Cepat**          | Eksekusi instan (detik vs hari di bank)      |  

---

#### **Platform Populer untuk Smart Contract**  
1. **Ethereum**  
   - Pionir smart contract.  
   - Bahasa: Solidity.  
   - Contoh: NFT, DeFi (Uniswap), DAO.  

2. **Binance Smart Chain (BSC)**  
   - Biaya gas lebih murah.  
   - Kompatibel dengan Ethereum.  

3. **Cardano**  
   - Fokus pada keamanan formal.  
   - Bahasa: Haskell.  

---

#### **Bahasa Pemrograman untuk Smart Contract**  
- **Solidity** (Ethereum, BSC): Paling populer, sintaks mirip JavaScript.  
- **Vyper** (Ethereum): Lebih sederhana, fokus ke keamanan.  
- **Rust** (Solana, Polkadot): High-performance, dipakai di blockchain generasi baru.  

#### **Contoh Kode Solidity**:  
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SimpleToken {
    string public name = "NazuCoin";
    string public symbol = "NAZU";
    uint8 public decimals = 18;
    uint256 public totalSupply = 1000000 * 10**decimals;
    
    mapping(address => uint256) private _balances;

    constructor() {
        _balances[msg.sender] = totalSupply;
    }

    function transfer(address to, uint256 amount) external {
        require(_balances[msg.sender] >= amount, "Saldo tidak cukup");
        _balances[msg.sender] -= amount;
        _balances[to] += amount;
    }

    function balanceOf(address account) external view returns (uint256) {
        return _balances[account];
    }
}
```
**Penjelasan:**  
- Kontrak ini membuat token sederhana dengan supply tetap 1 juta NAZU.  
- Fungsi `transfer()` memindahkan token antar alamat.  
- `balanceOf()` mengecek saldo dompet.  
- **Gas Estimate**:  
  - Deploy: ~1,200,000 gas (≈ $48 @ 40 Gwei)  
  - Transfer: 51,210 gas (≈ $2.05)  

---
#### **Kekurangan Smart Contract**  
1. **Immutability**  
   - Kode tidak bisa diubah setelah di-deploy → Jika ada bug, harus buat kontrak baru.  
2. **Biaya Gas**  
   - Eksekusi kontrak butuh bayar gas fee (contoh: di Ethereum).  
3. **Ketergantungan pada Data Eksternal**  
   - Butuh *oracle* (contoh: Chainlink) untuk akses data luar (harga saham, cuaca).  

---

#### **Masa Depan Smart Contract**  
- **DeFi** (Pinjam-meminjam tanpa bank).  
- **Game NFT** (Kepemilikan aset dalam game).  
- **Voting Online** (Transparan, anti kecurangan).  
- **IoT** (Mesin bayar listrik otomatis pakai crypto).  

Smart contract adalah **tulang punggung Web3**, mengubah cara kita berinteraksi dengan uang, kontrak, dan sistem terpercaya. Dari beli kopi sampai beli rumah, semua bisa otomatis tanpa pihak ketiga! 🚀


---

### **5. EVM & Gas: Bahan Bakar Blockchain**  
#### **Cara Kerja EVM**:  
1. Kontrak pintar dikompilasi ke **bytecode** (bahasa mesin EVM).  
2. EVM menjalankan bytecode langkah demi langkah.  
3. Setiap operasi (e.g., `ADD`, `STORE`) memakan **gas**.  

#### **Biaya Gas di Ethereum (2024)**:  
| Operasi               | Gas Used | Biaya (USD @ $2000/ETH) |  
|-----------------------|----------|--------------------------|  
| Transfer ETH          | 21,000   | $1.68                    |  
| Deploy ERC-20         | 1,200,000| $96                      |  
| Swap di Uniswap       | 150,000  | $12                      |  
| Mint NFT              | 80,000   | $6.40                    |  
| Transfer ERC-20       | 51,210   | $4.10                    |  

*Catatan: 1 gas = 40 Gwei = 0.00000004 ETH ($0.00008 @ $2000/ETH)*  

**Rumus Biaya Transaksi**:  
`Biaya = Gas Used × Gas Price`  
Contoh: 100,000 gas × 20 Gwei = 0.002 ETH.  

---

### **6. Struktur Block: Buku Resep Terenkripsi**  
Setiap block berisi:  
1. **Header**:  
   - **Parent Hash**: ID block sebelumnya.  
   - **Merkle Root**: Hash dari semua transaksi dalam block.  
   - **Nonce**: Angka acak yang ditemukan miner.  
2. **Body**:  
   - Daftar transaksi (2000+ transaksi per block di Bitcoin).  

#### **Merkle Tree**:  
- Transaksi di-hash berpasangan hingga tersisa satu hash (**Merkle root**).  
- Memungkinkan verifikasi transaksi tanpa mengunduh seluruh block.  

Merkle Tree: Contoh Real dengan 4 Transaksi**  
**Transaksi:**  
1. TX1: Alice → Bob (0.5 ETH)  
2. TX2: Charlie → Dave (1 ETH)  
3. TX3: Eve → Frank (3 ETH)  
4. TX4: Grace → Henry (2 ETH)  

**Proses Pembentukan Merkle Root:**  
```
Hash(TX1) = H1  
Hash(TX2) = H2  
Hash(TX3) = H3  
Hash(TX4) = H4  

Hash(H1+H2) = H12  
Hash(H3+H4) = H34  

Hash(H12+H34) = Merkle Root (0x5f4d3c...9876)
```

**Visualisasi:**  
```
      Merkle Root (H1234)  
       /        \  
     H12        H34  
    /   \      /   \  
  H1    H2   H3    H4  
  TX1  TX2  TX3   TX4
```

**Kode Python untuk Generate Merkle Root:**  
```python
import hashlib

def sha256(data):
    return hashlib.sha256(data.encode()).hexdigest()

txns = ["TX1", "TX2", "TX3", "TX4"]
hashes = [sha256(tx) for tx in txns]

while len(hashes) > 1:
    new_hashes = []
    for i in range(0, len(hashes), 2):
        pair = hashes[i] + (hashes[i+1] if i+1 < len(hashes) else hashes[i])
        new_hashes.append(sha256(pair))
    hashes = new_hashes

print("Merkle Root:", hashes[0])
```

### Validasi Merkle Proof (Light Client)
Sebuah light client hanya perlu memverifikasi apakah transaksi TX1 termasuk dalam block tanpa mengunduh seluruh blok:  
1. **Data yang Diberikan**:  
   - TX1  
   - H2  
   - H34  
   - Merkle Root dari header block  

2. **Proses Verifikasi**:  
   ```python
   h1 = sha256(TX1)
   h12 = sha256(h1 + H2)
   h1234 = sha256(h12 + H34)
   assert h1234 == merkle_root_block
   ```

Dengan contoh konkret ini, proses teknis blockchain menjadi lebih nyata. Setiap lapisan teknologi—dari kode smart contract hingga struktur merkle tree—bekerja bersama menciptakan sistem yang terdesentralisasi namun terpercaya.


---

### **7. Konsensus: Cara Node Bersepakat**  
#### **Proof of Work (PoW)**:  
- Miner bersaing memecahkan teka-teki matematis.  
- **Kelemahan**: Boros energi.  
- **Contoh**: Bitcoin, Dogecoin.  

#### **Proof of Stake (PoS)**:  
- Validator dipilih berdasarkan jumlah koin yang di-*stake*.  
- **Keuntungan**: Hemat energi.  
- **Contoh**: Ethereum 2.0, Cardano.  

**Perbandingan**:  
| Kriteria          | PoW               | PoW               |  
|--------------------|-------------------|-------------------|  
| Energi            | Tinggi            | Rendah            |  
| Kecepatan         | Lambat (~10 menit)| Cepat (~12 detik) |  
| Desentralisasi    | Tinggi            | Sedang            |  

---

### **8. Double-Spending & Konsensus**  
#### **Masalah Double-Spending**:  
- Bagaimana jika Anda mencoba mengirim 1 ETH ke dua orang sekaligus?  
- **Solusi**: Blockchain memilih rantai terpanjang (dengan kerja terbanyak).  

#### **Serangan 51%**:  
- Jika satu entitas mengontrol >51% kekuatan mining, mereka bisa memanipulasi transaksi.  
- **Contoh**: Bitcoin Gold pernah diserang tahun 2018.  

---

### **9. Masa Depan Blockchain & Web3**  
#### **Aplikasi Nyata**:  
- **DeFi** (*Decentralized Finance*): Pinjam atau pinjamkan uang tanpa bank.  
- **DAOs** (*Decentralized Autonomous Organizations*): Perusahaan yang dijalankan oleh kode.  
- **Metaverse**: Kepemilikan aset digital (NFT) yang terverifikasi.  

#### **Tantangan**:  
- **Skalabilitas**: Ethereum hanya bisa memproses 15–30 transaksi/detik (vs Visa: 24.000/detik).  
- **Regulasi**: Pemerintah masih mencari cara mengatur blockchain.  

---

### **Kesimpulan: Blockchain = Dapur Masa Depan**  
Blockchain bukan hanya teknologi—ia adalah revolusi cara kita berinteraksi dan mempercayai. Dengan memahami dasarnya, Anda siap menjadi "koki" di era Web3!  

**Referensi**:  
- [Buku Putih Bitcoin](https://bitcoin.org/bitcoin.pdf)  
- [Dokumentasi Ethereum](https://ethereum.org/en/developers/docs/)  
- [Simulator Blockchain Interaktif](https://andersbrownworth.com/blockchain/)  

**Catatan**:  
- ¹ 1 Gwei = 0.000000001 ETH.  
- ² Hash adalah *digital fingerprint* unik dari data.

