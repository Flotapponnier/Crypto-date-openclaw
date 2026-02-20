# 🚀 Quick Start - Mobula Skill pour OpenClaw

## ✅ Ta clé API fonctionne !

J'ai testé ta clé API : `924f2fa8-6129-4e86-a1fd-bc32950c2cd1` ✅

**Résultat des tests :**
- ✅ Bitcoin price : **$67,529** (fonctionne)
- ✅ BRETT on Base : **$0.00783** (fonctionne)
- ✅ API accessible

---

## 📋 Installation en 3 étapes

### Étape 1 : Configure ta clé API

```bash
# Ajoute ça à ton shell config
echo 'export MOBULA_API_KEY="924f2fa8-6129-4e86-a1fd-bc32950c2cd1"' >> ~/.zshrc
source ~/.zshrc

# Vérifie que c'est bien configuré
echo $MOBULA_API_KEY
# Devrait afficher : 924f2fa8-6129-4e86-a1fd-bc32950c2cd1
```

### Étape 2 : Installe OpenClaw (si pas déjà fait)

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon
```

### Étape 3 : Installe le skill Mobula

**Option A : Via URL (recommandé)**
```bash
# Dis à ton agent OpenClaw (via Telegram/WhatsApp/etc.) :
"Install skill from https://raw.githubusercontent.com/Flotapponnier/Crypto-date-openclaw/main/SKILL.md"
```

**Option B : Manuel**
```bash
cd ~/openclaw/skills/
mkdir mobula
cd mobula
curl -o SKILL.md https://raw.githubusercontent.com/Flotapponnier/Crypto-date-openclaw/main/SKILL.md
```

Puis redémarre l'agent :
```bash
openclaw restart
```

---

## 🎮 Test immédiat

Une fois installé, teste avec ces commandes dans ton app de messagerie (Telegram, WhatsApp, etc.) :

### Test 1 : Prix simple
```
What's the price of Bitcoin?
```

**Réponse attendue :**
```
Bitcoin (BTC) is currently $67,529 (↑1.58% 24h).

Market data:
- Market cap: $1.35T
- Volume 24h: $115M
- 7d change: -1.96%

Bitcoin is grinding higher after recent volatility.
```

### Test 2 : Token sur une chain spécifique
```
Get BRETT price on Base
```

**Réponse attendue :**
```
Brett (BRETT) on Base

Price: $0.00783 (↑9.0% 24h)
Market cap: $77.6M
Liquidity: $1.23M
Volume 24h: $6.27M

Contract: 0x532f27101965dd16442e59d40670faf5ebb142e4
```

### Test 3 : Wallet portfolio
```
Show portfolio for wallet 0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045
```

**Réponse attendue :**
L'agent va lister tous les tokens détenus par ce wallet sur toutes les chains.

---

## 🔥 Exemples d'utilisation avancée

### Compare plusieurs tokens
```
Compare Bitcoin, Ethereum, and Solana performance today
```

L'agent va :
1. Appeler `/api/1/market/data` pour BTC
2. Appeler `/api/1/market/data` pour ETH
3. Appeler `/api/1/market/data` pour SOL
4. Comparer et synthétiser

### Analyse complète d'un token
```
Analyze this token: 0x532f27101965dd16442e59d40670faf5ebb142e4 on Base
```

L'agent va :
1. Market data (prix, volume, mcap)
2. Historique 7j et 30j
3. Trades récents (accumulation vs distribution)
4. Metadata (projet, socials)
5. Synthèse avec assessment

### Setup monitoring proactif
```
Monitor my wallet 0xYourWallet and alert me on Telegram if:
- Any token drops more than 15% in 24h
- My allocation on one token exceeds 40%
- Send me a daily summary at 9am
```

L'agent va créer un heartbeat qui tourne 24/7.

---

## 💎 Heartbeat templates prêts à l'emploi

### Portfolio Guardian

1. Copie le template :
```bash
curl -o ~/openclaw/heartbeat/portfolio-guardian.md https://raw.githubusercontent.com/Flotapponnier/Crypto-date-openclaw/main/examples/heartbeat-portfolio-guardian.md
```

2. Édite le fichier :
```bash
nano ~/openclaw/heartbeat/portfolio-guardian.md
```

3. Remplace `YOUR_WALLET_ADDRESS_HERE` par ton wallet

4. Redémarre :
```bash
openclaw restart
```

5. **C'est tout !** L'agent va monitorer ton wallet toutes les 30 minutes automatiquement.

### Whale Tracker

```bash
curl -o ~/openclaw/heartbeat/whale-tracker.md https://raw.githubusercontent.com/Flotapponnier/Crypto-date-openclaw/main/examples/heartbeat-whale-tracker.md
```

Édite et ajoute les wallets whales que tu veux suivre.

### Token Scout

```bash
curl -o ~/openclaw/heartbeat/token-scout.md https://raw.githubusercontent.com/Flotapponnier/Crypto-date-openclaw/main/examples/heartbeat-token-scout.md
```

Trouve automatiquement de nouveaux tokens selon tes critères toutes les 6h.

### Market Brief

```bash
curl -o ~/openclaw/heartbeat/market-brief.md https://raw.githubusercontent.com/Flotapponnier/Crypto-date-openclaw/main/examples/heartbeat-market-brief.md
```

Reçois un résumé du marché crypto tous les matins à 8h.

---

## 🧪 Commandes de test en live

### Test API directement (sans OpenClaw)

**Bitcoin price :**
```bash
curl -H "Authorization: 924f2fa8-6129-4e86-a1fd-bc32950c2cd1" \
  "https://api.mobula.io/api/1/market/data?asset=Bitcoin"
```

**Ethereum price :**
```bash
curl -H "Authorization: 924f2fa8-6129-4e86-a1fd-bc32950c2cd1" \
  "https://api.mobula.io/api/1/market/data?asset=Ethereum"
```

**BRETT on Base :**
```bash
curl -H "Authorization: 924f2fa8-6129-4e86-a1fd-bc32950c2cd1" \
  "https://api.mobula.io/api/1/market/data?asset=BRETT&blockchain=Base"
```

**Wallet portfolio :**
```bash
curl -H "Authorization: 924f2fa8-6129-4e86-a1fd-bc32950c2cd1" \
  "https://api.mobula.io/api/1/wallet/portfolio?wallet=0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045"
```

---

## 📊 Ce que tu vas pouvoir faire

### 1. Monitoring en temps réel
- Track ton portfolio 24/7
- Alertes instantanées sur Telegram/WhatsApp
- Résumés quotidiens automatiques

### 2. Whale tracking
- Suis les smart money wallets
- Détecte les accumulations coordonnées
- Copie les mouvements des whales

### 3. Token discovery
- Trouve automatiquement de nouveaux tokens
- Selon tes critères (mcap, liquidity, volume)
- Scan continu des chains Base, Arbitrum, etc.

### 4. Analyse on-demand
- "Should I buy this token?"
- "Compare these 5 tokens"
- "What's the sentiment on this wallet?"

### 5. Market intelligence
- Briefings quotidiens
- Comparaisons cross-chain
- Détection de trends

---

## ⚡ Limites à connaître

### Rate limits (free tier)
- **100 requests/minute**
- Pour monitoring intensif : utilise les endpoints batch
- Exemple : `/api/1/market/multi-data?assets=BTC,ETH,SOL` (1 call au lieu de 3)

### Heartbeat optimization
- 1 heartbeat toutes les 30min = ~50 requests/jour
- 5 wallets monitorés = 250 requests/jour
- Reste largement sous la limite

### Upgrade si nécessaire
Si tu dépasses les limites, upgrade sur [admin.mobula.fi](https://admin.mobula.fi)

---

## 🐛 Troubleshooting

### "API key not found"
```bash
# Vérifie que la variable est bien set
echo $MOBULA_API_KEY

# Si vide, re-configure
export MOBULA_API_KEY="924f2fa8-6129-4e86-a1fd-bc32950c2cd1"
```

### "Skill not found"
```bash
# Vérifie que le skill existe
ls ~/openclaw/skills/mobula/SKILL.md

# Si absent, réinstalle
cd ~/openclaw/skills/mobula
curl -o SKILL.md https://raw.githubusercontent.com/Flotapponnier/Crypto-date-openclaw/main/SKILL.md
```

### "Agent doesn't use the skill"
Sois explicite dans ta requête :
```
Use Mobula to check Bitcoin price
```

Ou redémarre l'agent :
```bash
openclaw restart
```

### Heartbeat ne tourne pas
```bash
# Vérifie que le fichier est bien placé
ls ~/openclaw/heartbeat/

# Vérifie le frontmatter :
# enabled: true
# interval: 30

# Redémarre
openclaw restart
```

---

## 📚 Ressources

- **Repo GitHub :** [Crypto-date-openclaw](https://github.com/Flotapponnier/Crypto-date-openclaw)
- **Documentation complète :** [HOW_IT_WORKS.md](./docs/HOW_IT_WORKS.md)
- **API Mobula docs :** [docs.mobula.io](https://docs.mobula.io)
- **Dashboard Mobula :** [admin.mobula.fi](https://admin.mobula.fi)

---

## 🎉 Tu es prêt !

Maintenant tu as :
✅ Une clé API qui fonctionne
✅ Le skill Mobula installé
✅ Des exemples concrets
✅ Des templates heartbeat
✅ La doc complète

**Lance OpenClaw et teste :** "What's the price of Bitcoin?" 🚀
