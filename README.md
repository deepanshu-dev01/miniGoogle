# 🌐 miniGoogle

A lightweight, interactive search engine simulator comparing **pre-1998 keyword frequency ranking** (AltaVista/Lycos style) against **Google's PageRank algorithm** (Larry Page & Sergey Brin, Stanford 1998). Built with **HTML5, CSS3, and Vanilla JavaScript**.

![miniGoogle Preview](https://img.shields.io/badge/miniGoogle-PageRank%20Engine-1a73e8?style=for-the-badge&logo=google)

---

## ⚡ Why miniGoogle?

In the early days of the web (1994–1997), search engines ranked websites primarily by **Term Frequency (TF)**—how often a search word appeared on a page. Webmasters quickly exploited this with **keyword stuffing**: repeating a word like *"pizza"* 50 to 100 times in hidden white text to hijack the #1 ranking.

In 1998, Larry Page and Sergey Brin introduced **PageRank**, treating the web as a directed graph where **hyperlinks act as peer endorsements (votes of confidence)**. A spam site with 0 incoming backlinks receives virtually no authority, no matter how many times it repeats a keyword, while reputable hubs with links from multiple domains rise to the top.

**miniGoogle visually and interactively demonstrates this exact paradigm shift.**

---

## 🚀 Features

### 🔍 1. Side-by-Side Search Comparison
- **Old Way (Pre-1998)**: Documents ranked purely by keyword count (TF). Vulnerable to keyword stuffing.
- **miniGoogle PageRank (1998+)**: Documents ranked by a hybrid of keyword relevance and backlink graph authority.

### ➕ 2. Dynamic "Add Page" Simulator
- Add new custom websites to the web graph dynamically!
- Choose domain name, page title, meta snippet, and body content.
- Pick **outbound hyperlinks** (which existing pages the new page links to).
- Pick **inbound backlinks** (which existing pages link to this new page).
- Pre-fill with one-click presets:
  - 🚨 *Keyword Spam Site* (Demonstrates how high frequency + 0 backlinks ranks #1 on Old Way but drops to bottom on PageRank).
  - 🏆 *Authoritative Food Guide* (Demonstrates high authority from peer links).
  - 🎓 *Student Tech Blog*
- Real-time recalculation of PageRank power iteration, rankings, SVG graph, and convergence table!

### 🕸️ 3. Interactive Web Link Graph (SVG)
- Symmetrical circular network graph displaying all indexed web pages.
- Directed curved arrows illustrating outbound links and inbound backlinks.
- Node sizes scale dynamically based on calculated PageRank percentage.
- Click any node to highlight incoming endorsements (green) and outgoing votes (blue).

### 🧮 4. Mathematical Convergence & Damping Factor Slider
- Step-by-step mathematical explanation of the PageRank formula:
  $$\text{PR}(u) = \frac{1 - d}{N} + d \sum_{v \in B(u)} \frac{\text{PR}(v)}{L(v)}$$
- Interactive slider to adjust the damping factor $d$ ($0.50$ to $0.95$, default $0.85$).
- Live convergence matrix showing exact decimal scores, link counts, and percentage shares.

### 📄 5. In-Browser Webpage Inspector
- Click "Inspect ↗" on any result card to view the simulated rendered HTML webpage, outgoing hyperlinks, and metadata.

---

## 🌐 The 6 Default Indexed Websites

| ID | Domain | Outbound Links | Inbound Backlinks | Initial PageRank | Role / Description |
|:---|:---|:---|:---|:---|:---|
| **P1** | `pune-food-guide.com` | P2 | P2, P6 | **21.32%** | City food directory & local culinary guide |
| **P2** | `best-pizza-pune.com` | P1, P3 | P1, P3, P4, P5 | **39.29%** | **Top Authority Hub** (Endorsed by 4 websites) |
| **P3** | `college-canteen-blog.com` | P2, P4 | P2 | **19.20%** | Student campus food & cheap snack blog |
| **P4** | `pizza-recipes-home.com` | P2, P5 | P3 | **10.66%** | Artisan pizza dough & home baking recipes |
| **P5** | `cheap-eats-pune.com` | P2 | P4 | **7.03%** | Budget food & street cart guide |
| **P6** | `pizza-pizza-pizza.com` | P1 | *None (0)* | **2.50%** | **Spam site** (Repeats "pizza" 45 times, 0 backlinks) |

---

## 🍕 The Landmark "Pizza" Search Test

1. Type **`pizza`** into the search bar.
2. **Old Search Engine Result**:
   - `pizza-pizza-pizza.com` ranks **#1** with 45 keyword matches! (Spam wins).
3. **miniGoogle PageRank Result**:
   - `best-pizza-pune.com` ranks **#1** (39.3% authority, endorsed by 4 websites).
   - `pizza-pizza-pizza.com` plunges to the bottom (0 backlinks, only 2.5% baseline score).

---

## 🛠️ Getting Started

Open `index.html` or `miniGoogle.html` directly in any web browser:

```bash
# Clone the repository
git clone https://github.com/deepanshu-dev01/miniGoogle.git

# Enter project directory
cd miniGoogle

# Open in browser (macOS)
open index.html
```

---

## 📜 Tech Stack

- **HTML5**: Semantic tags, accessible forms, SVG canvas.
- **CSS3**: Google-style design system, responsive split grid, badge indicators, subtle animations.
- **JavaScript (Vanilla)**: Matrix power iteration, dynamic graph layout, real-time string tokenization & keyword counting. Zero external dependencies.
