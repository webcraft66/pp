# Patliputra VinFast website

Ek static website (index.html + images) aur AI chat ke liye ek chhota Vercel function (`api/chat.js`).
Koi build step nahi hai, koi database nahi hai.

## Folder mein kya hai
- `index.html` : poori website (3D car, models, offers, EMI, test drive form, FAQ, chatbot). Photos isi file ke andar embedded hain.
- `images/`    : cropped photos ki copy (baad mein kahin aur use karne ke liye).
- `api/chat.js`: AI chat ka server code. Sirf Vercel par chalta hai.
- `package.json`, `.gitignore`, `.env.example` : project ki settings.

## 1. Laptop par dekhna (sabse aasaan)
1. Zip par right-click > **Extract All** (Mac: double-click). Zip ke andar se seedha mat kholna.
2. Folder mein `index.html` par double-click karo. Chrome mein khulega.
3. 3D car ke liye internet chahiye (three.js aur GSAP online se aate hain).
4. Chat mein pre-set jawab chalenge. AI jawab sirf Vercel par live hone ke baad chalenge.

Chaho to server ke saath dekho: Node.js install karo (nodejs.org, LTS) aur folder mein terminal kholkar `npm run dev` chalao, phir http://localhost:3000 kholo.

## 2. Apni details badalna
`index.html` ko Notepad/VS Code mein kholo. Upar script ke andar `CONFIG` block hai: naam, WhatsApp number (country code ke saath, sirf digits: 919231445060), phone, email, address, hours, vehicles ke prices aur specs. Sirf wahi badlo, baaki mat chhedo. Prices badlo to `api/chat.js` ke andar bhi badlo.

## 3. GitHub par daalna
1. github.com par account banao (free).
2. Upar `+` > **New repository**. Naam: `patliputra-vinfast`. **Public** ya **Private**, dono chalenge. **Create repository**.
3. **uploading an existing file** link par click karo.
4. Extract kiye hue folder ke **andar ki saari cheezein** (`index.html`, `images`, `api`, `package.json`, `.gitignore`, `.env.example`, `README.md`) drag karke daalo. Zip file ya bahar wala folder mat daalo. `api` folder ka andar `chat.js` dikhna chahiye.
5. Neeche **Commit changes** dabao.

(Git aata ho to: folder mein terminal kholo, `git init`, `git add .`, `git commit -m "first"`, `git branch -M main`, `git remote add origin <repo-link>`, `git push -u origin main`.)

## 4. Vercel par live karna
1. vercel.com > **Sign Up** > **Continue with GitHub**.
2. **Add New > Project**, apni `patliputra-vinfast` repository ke saamne **Import**.
3. Framework Preset: **Other**. Build Command aur Output Directory **khali** chhodo.
4. **Deploy** dabao. 1 minute mein live link milega (jaise `patliputra-vinfast.vercel.app`).
5. Aage badlaav ke liye GitHub par file edit karo (pencil icon > Commit). Vercel apne aap dobara deploy kar dega.

## 5. AI chat chalu karna
1. console.anthropic.com par account banao, **API Keys** se key banao, aur **Billing/Limits** mein ek monthly spend limit lagao.
2. Vercel > apna project > **Settings > Environment Variables**: Name `ANTHROPIC_API_KEY`, Value woh key. Save.
3. **Deployments** > latest ke saamne `...` > **Redeploy**.
4. Site kholo, chat mein koi aisa sawaal poochho jo pre-set na ho (jaise "exchange karte ho?"). AI ka jawab aana chahiye.
Bina key ke bhi chat chalta hai, bas AI wale sawaalon par "Ask our team on WhatsApp" button dikhata hai.

## 6. Live karne se pehle check karo
- Test drive form bharo aur dekho WhatsApp message sahi number (+91 92314 45060) par ja raha hai.
- Chat mein "Book a test drive" poora chalao.
- Phone par site kholkar 3D car, menu aur neeche ki Call/WhatsApp bar dekho.
- Prices aur offers abhi bhi sahi hain, client se confirm karo. Limo Green ke specs baaki hain.
- Photos screenshots se bani hain, asli high-quality photos mile to badal do. Photos aur VinFast ki images use karne ki permission client se lo.

## Aam dikkatein
- **Chat mein AI jawab nahi aa raha:** `api` folder GitHub par root mein hai? Key sahi daali? Key daalne ke baad Redeploy kiya?
- **3D car nahi dikh rahi:** internet check karo, ya purana phone ho to halka mode chahiye, mujhe batao.
- **Vercel par 404:** `index.html` repository ke root mein hona chahiye, kisi folder ke andar nahi.
- **Images nahi dikh rahi:** photos `index.html` ke andar hain; file poori upload hui ya nahi dekho.

## Dhyan rakhna
Vercel ka free Hobby plan sirf personal, non-commercial use ke liye hai. Client ki asli business site ke liye Vercel Pro (paid) lo, ya kisi aur hosting par daalo aur uski terms padho.
