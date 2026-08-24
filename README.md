# ⚡️ 𝗔𝗟𝗣𝗛𝗔 𝗨𝗦𝗘𝗥𝗕𝗢𝗧 ⚡️

<p align="center">
  <b>POWERED BY TEAMPURVI & RAUSHAN KING ARA</b>
</p>

---

## 🚀 Depoyment Guide (कैसे Deploy करें)

Alpha Userbot को deploy करने के आसान तरीके नीचे दिए गए हैं। आप इसे **Heroku**, **Render**, या अपने **VPS / Local Server / Docker** पर आसानी से सेट अप कर सकते हैं।

---

### 1️⃣ Deployment on Heroku (हीरोकु पर डिप्लॉय करें)

1. सबसे पहले Telegram पर [@StringFatherRobot](https://t.me/StringFatherRobot) या Pyrogram String Session generator से अपनी **Pyrogram String Session** निकालें।
2. नीचे दिए गए **Deploy to Heroku** बटन पर क्लिक करें:

   [![Deploy To Heroku](https://www.herokucdn.com/deploy/button.svg)](https://dashboard.heroku.com/new?template=https://github.com/TEAMPURVI/ALPHA_USERBOT)

3. App Name दर्ज करें और मांगी गई **Environment Variables** (जैसे `API_ID`, `API_HASH`, `STRING_SESSION1`, `BOT_TOKEN`, `MONGO_URL`, `OWNER_ID`) भरें।
4. **Deploy App** पर क्लिक करें और बिल्ड पूरा होने का इंतजार करें।
5. Deploy पूरा होने के बाद **Dynos** टैब में जाकर `worker` dyno को Enable (ON) करें।

---

### 2️⃣ Deployment on Render (रेंडर पर डिप्लॉय करें)

1. [Render.com](https://render.com) पर साइन अप / लॉगिन करें।
2. नीचे दिए गए **Deploy to Render** बटन पर क्लिक करें:

   [![Deploy To Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/TEAMPURVI/ALPHA_USERBOT)

3. Render की सेटिंग्स में अपने सभी **Environment Variables** जोड़ें।
4. **Create Web Service** पर क्लिक करें। Render अपने आप Docker Image तैयार करके सर्विस स्टार्ट कर देगा।

---

### 3️⃣ Deployment on VPS / Docker / Local Machine (सर्वर या वीपीएस पर)

#### Option A: Docker के जरिए (Recommended)
```bash
# 1. रिपॉजिटरी क्लोन करें
git clone https://github.com/TEAMPURVI/ALPHA_USERBOT
cd ALPHA_USERBOT

# 2. Docker Image बनाएं
docker build -t alpha-userbot .

# 3. Docker Container चलाएं
docker run -d --name alpha_userbot alpha-userbot
```

#### Option B: Manual Setup (Local Server / VPS)
```bash
# 1. रिपॉजिटरी क्लोन करें
git clone https://github.com/TEAMPURVI/ALPHA_USERBOT
cd ALPHA_USERBOT

# 2. Python Virtual Environment बनाएं और एक्टिवेट करें (Optional)
python3 -m venv venv
source venv/bin/activate

# 3. आवश्यक Dependencies इंस्टॉल करें
pip3 install -U -r requirements.txt

# 4. Environment Variables सेट करें (local.env या .env फ़ाइल बनाएं)
cp sample.env local.env
# local.env में अपनी डिटेल्स भरें

# 5. बोट चालू करें
bash start.sh
```

---

## 🔑 Required Environment Variables (आवश्यक वेरिएबल्स)

| Variable | Description (विवरण) | Required? |
| :--- | :--- | :---: |
| `API_ID` | my.telegram.org से प्राप्त करें | Yes |
| `API_HASH` | my.telegram.org से प्राप्त करें | Yes |
| `STRING_SESSION1` | @StringFatherRobot से निकाली गई Pyrogram String Session | Yes |
| `BOT_TOKEN` | @BotFather से प्राप्त Telegram Bot Token | Yes |
| `MONGO_URL` | MongoDB Database URL (MongoDB Atlas से निःशुल्क प्राप्त करें) | Yes |
| `OWNER_ID` | आपका Telegram User ID | Yes |
| `SUDO_USERS` | Sudo यूज़र्स के IDs (स्पेस या कॉमा द्वारा अलग किए गए) | Optional |
| `ALIVE_PIC` | .alive कमांड के लिए कस्टम फोटो लिंक | Optional |
| `ALIVE_TEXT` | .alive कमांड के लिए कस्टम टेक्स्ट | Optional |

---

## 📜 All Commands List (सभी कमांड्स की सूची)

सभी कमांड्स के आगे डिफॉल्ट प्रीफिक्स `.` (Dot) का उपयोग किया जाता है।

### ⚙️ 1. Basic & System Commands (मूल कमांड्स)
- `.ping` - बोट की स्पीड और रिस्पॉन्स टाइम चेक करें।
- `.alive` - बोट का ऑनलाइन स्टेटस और विवरण देखें।
- `.help` / `.helpme` - सहायता मेनू और सभी मॉड्यूल्स की सूची देखें।
- `.plugins` / `.modules` - लोड किए गए प्लगइन्स की सूची देखें।
- `.sysinfo` / `.stats` - सर्वर और बोट के सिस्टम आंकड़े देखें।
- `.afk [reason]` - AFK (Away From Keyboard) मोड ऑन करें।

### 👮‍♂️ 2. Administrator Commands (एडमिन कमांड्स)
- `.ban <reply/username/userid>` - ग्रुप से यूज़र को बैन करें।
- `.unban <reply/username/userid>` - बैन यूज़र को अनबैन करें।
- `.mute <reply/username/userid>` - यूज़र को म्यूट (मौन) करें।
- `.unmute <reply/username/userid>` - यूज़र को अनम्यूट करें।
- `.kick <reply/username/userid>` - यूज़र को ग्रुप से बाहर (किक) करें।
- `.pin` - रिप्लाई किए गए मैसेज को पिन करें।
- `.unpin` - पिन मैसेज को अनपिन करें।
- `.purge` - रिप्लाई किए गए मैसेज के बाद के सभी मैसेज डिलीट करें।
- `.del` - रिप्लाई किए गए मैसेज को डिलीट करें।
- `.promote` - यूज़र को एडमिन बनाएं।
- `.demote` - एडमिन पद से हटाएं।
- `.invite` - यूज़र को ग्रुप में ऐड करें।
- `.adminlist` - ग्रुप के सभी एडमिन्स की लिस्ट देखें।
- `.locks` / `.lock` / `.unlock` - ग्रुप की सेटिंग्स (media, sticker, etc.) लॉक/अनलॉक करें।

### 🛡️ 3. Anti-PM & PM Security (पीएम गार्ड कमांड्स)
- `.pmguard [on/off]` - Anti-PM प्रोटेक्शन ऑन या ऑफ करें।
- `.allow` / `.a` - यूज़र को आपके पर्सनल मैसेज (PM) में बात करने की अनुमति दें।
- `.deny` / `.da` - यूज़र की अनुमति रद्द करें / ब्लॉक करें।
- `.setpmmsg [msg/default]` - कस्टम PM मैसेज सेट करें।
- `.setblockmsg [msg/default]` - लिमिट पार होने पर कस्टम ब्लॉक मैसेज सेट करें।
- `.setlimit [num]` - अनऑथराइज्ड मैसेज की मैक्सिमम लिमिट सेट करें।

### 🌐 4. Global Banning & Sudo (ग्लोबल और सुडो कमांड्स)
- `.gban <reply/username/userid>` - यूज़र को आपके सभी ग्रुप्स में ग्लोबली बैन करें।
- `.ungban <reply/username/userid>` - ग्लोबल बैन हटाएं।
- `.listgban` - ग्लोबली बैन किए गए यूज़र्स की सूची देखें।
- `.addsudo <reply/username/userid>` - नए सुडो (Sudo) यूज़र को जोड़ें।
- `.rmsudo <reply/username/userid>` - सुडो एक्सेस हटाएं।
- `.sudolist` - सभी सुडो यूज़र्स की लिस्ट देखें।

### 🚀 5. Spam & Raid Commands (स्पैम एवं रेड कमांड्स)
- `.spam <count> <text>` - एक साथ दिए गए टेक्स्ट को बार-बार स्पैम करें।
- `.delayspam <delay> <count> <text>` - समय अंतराल (delay) के साथ स्पैम करें।
- `.dmspam <username> <count> <text>` - किसी यूज़र के PM में स्पैम करें।
- `.dmraid <username> <count>` - PM में रेड करें।
- `.raid <count> <user>` - ग्रुप में टारगेट यूज़र पर रेड चलाएं।
- `.replyraid` - टारगेट यूज़र के हर मैसेज पर ऑटोमैटिक रेड/रिप्लाई सेट करें।
- `.dreplyraid` - रिप्लाई रेड बंद करें।
- `.pornspam <count>` - पोर्न स्पैम भेजें।

### 🎨 6. Fun & Utilities (मनोरंजन एवं उपयोगिता)
- `.carbon <text>` - टेक्स्ट का सुंदर कोड/इमेज कार्ड बनाएं।
- `.telegraph` - मीडिया फ़ाइल या टेक्स्ट को Telegraph लिंक में बदलें।
- `.quote` / `.q` - मैसेज को स्टिकर कोट (Quote) में बदलें।
- `.song` / `.music <name>` - मनपसंद गाना ढूंढकर डाउनलोड करें।
- `.lyrics <song name>` - गाने के बोल (Lyrics) खोजें।
- `.tr <lang_code>` - मैसेज का अनुवाद (Translate) करें।
- `.ud <word>` - Urban Dictionary से शब्द का अर्थ खोजें।
- `.google <query>` / `.ggl` - गूगल सर्च लिंक प्राप्त करें।
- `.weather <city>` - मौसम की जानकारी देखें।
- `.screenshot` / `.ss <url>` - किसी वेब पेज का स्क्रीनशॉट लें।

### 🎙️ 7. Voice Chat (VC Tools)
- `.vcjoin` - ग्रुप वॉइस चैट (VC) में शामिल हों।
- `.vcleave` - वॉइस चैट से बाहर निकलें।

### 🔄 8. Updater & Maintenance
- `.update` - नए अपडेट्स की जांच करें।
- `.update deploy` - बोट को नवीनतम वर्शन में अपडेट व री-डिप्लॉय करें।
- `.restart` - यूज़रबोट को रीस्टार्ट करें।

---

## 🤝 Support & Channel (सहायता एवं अपडेट्स)

- **Support Group:** [@PURVI_BOTS](https://t.me/PURVI_BOTS)
- **Updates Channel:** [@PURVI_UPDATES](https://t.me/PURVI_UPDATES)
- **Owner / Creator:** [@ll_ALPHA_BABY_lll](https://t.me/ll_ALPHA_BABY_lll)

---
<p align="center">
  <b>🚩🚩 जय बजरंग बली 🚩🚩</b>
</p>
