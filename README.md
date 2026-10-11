# 💶 App Finanças

> A personal finance mobile app that splits your money into "envelopes" and shows how much you can spend **today**, so you can save consistently and stop impulse purchases.

![Status](https://img.shields.io/badge/status-in%20development-yellow)
![Expo](https://img.shields.io/badge/Expo-React%20Native-000020?logo=expo)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)

---

## 📌 About

Most finance apps show your total account balance, which gives a false sense of how much money is actually available. This app does the opposite: when money comes in, it first sets aside what's committed (fixed expenses, yearly expenses and savings) and only then shows what's left, split across the days until the next income.

**No bank connection.** The user enters the balance and transactions manually, and all data stays on the device only.

A personal project, also built as a learning exercise in mobile development, testing and Git best practices.

## ✨ Features

### Planned for the MVP
- [ ] Fixed expenses setup (fixed amount, or variable with an average)
- [ ] Yearly expenses fund (e.g. taxes, car inspection, maintenance), set aside monthly
- [ ] Configurable savings rate, applied as soon as income arrives
- [ ] Extra income tracking, with a configurable share going to savings
- [ ] Separate envelope for meal card balance
- [ ] Home screen showing the amount **available today**
- [ ] Warning when an expense doesn't fit the budget
- [ ] Backup export and import (JSON)

### Future ideas
- [ ] Wishlist with a 48-hour cooling-off period before buying
- [ ] Monthly trend charts
- [ ] Savings goals with progress tracking

## 🧮 How the allocation works

```
Income received
 ├─ 1. Fixed expenses        (set aside)
 ├─ 2. Variable expenses     (average + buffer)
 ├─ 3. Yearly expenses fund  (yearly total ÷ 12)
 ├─ 4. Savings               (% of income)
 └─ 5. Free to spend         → split across the days until next income
```

Extra income follows its own rule: a percentage goes to savings and the rest is added to the free-to-spend amount.

## 🔒 Privacy

- No real financial data is, or ever will be, stored in this repository.
- Values are entered in the app and stored **locally** on the device.
- No server, no user accounts, no bank connections.
- Tests use fictional values only.

## 🛠️ Tech stack

| Area | Technology |
|---|---|
| Framework | [Expo](https://expo.dev) (React Native) |
| Language | TypeScript |
| Testing | Jest |
| Storage | SQLite (local) |
| Distribution | Expo Go (development) · PWA (daily use) |

## 🚀 Getting started

**Prerequisites:** Node.js (LTS) and the [Expo Go](https://expo.dev/go) app on your phone.

```bash
git clone https://github.com/<filipalimaa>/app-financas.git
cd app-financas
npm install
npx expo start
```

Scan the QR code with your phone's camera to open the app in Expo Go. Your computer and phone must be on the same Wi-Fi network.

### Tests
```bash
npm test
```

## 🗂️ Project structure (planned)

```
src/
 ├─ core/        # allocation logic (pure TypeScript, no UI dependencies)
 ├─ storage/     # local persistence
 ├─ screens/     # app screens
 └─ components/  # reusable components
__tests__/       # unit tests
```

## 🌿 Workflow

- `main`: stable version. Only receives merges from `develop`.
- `develop`: integration of ongoing work.
- Working branches are created from `develop`:
  - `feat/...` for new features
  - `fix/...` for bug fixes
  - `test/...` for tests
  - `docs/...` for documentation
  - `chore/...` for setup and maintenance

Commits follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) (e.g. `feat: calculate daily free-to-spend amount`).

## 🗺️ Roadmap

| Phase | Description | Status |
|---|---|---|
| 0 | Project setup, repository and documentation | 🟡 In progress |
| 1 | Allocation engine with tests (Jest) | ⚪ |
| 2 | Screens: setup, home and transaction entry | ⚪ |
| 3 | Local persistence and backups | ⚪ |
| 4 | Extras (charts, wishlist) and PWA release | ⚪ |

## 👩‍💻 Author

**Filipa**: [GitHub](<https://github.com/filipalimaa>) · [LinkedIn](<https://www.linkedin.com/in/filipaalima/>)

## 📄 License

Distributed under the MIT License. See [`LICENSE`](LICENSE).