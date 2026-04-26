# Judo Exameneisen Dashboard - Judoclub Michigami Steenbergen

Interactief dashboard voor het bekijken van exameneisen per band en slip, ontwikkeld met Kimi K2.6.

## Wat is dit?

Een web-tool die leerlingen en ouders overzichtelijk laat zien wat er bij elk examen hoort:
- **Welke technieken** ze moeten kennen (japanse namen + Nederlandse vertaling)
- **Hoeveel worpen** per categorie (beenworpen, heupworpen, schouderworpen, etc.)
- **Nage-komi eisen** (aantal herhaalde worpen in 1 minuut)
- **Kanteltechnieken & valbreektechnieken**

## Bandenstructuur

| Band | Kyu | Omschrijving |
|------|-----|--------------|
| Wit | 6 | Startniveau |
| Wit + gele slip | - | Tussenstap |
| Geel | 5 | Eerste kleurband |
| Geel + oranje slip | - | Tussenstap |
| Oranje | 4 | Midden-niveau |
| Oranje + groene slip | - | Tussenstap |
| Groen | 3 | Hoog niveau |
| Groen + blauwe slip | - | Tussenstap |
| Blauw | 2 | Bijna bruin |
| Blauw + bruine slip | - | Tussenstap |
| Bruin | 1 | Hoogste kyu-graden |

## Techniek-categorieën

### Ukemi-waza (Valbreektechnieken)
Direct vanaf witte band: 4 technieken

### Nage-waza (Werptechnieken)
- **Ashi-waza** - Beenworpen
- **Koshi-waza** - Heupworpen
- **Kata-waza** - Schouderworpen
- **Te-waza** - Armworpen
- **Sutemi-waza** - Offerworpen

### Katame-waza (Controletechnieken)
- **Osaekomi-waza** - Houdgrepen
- **Shime-waza** - Wurgingen
- **Kansetsu-waza** - Armklemmen

## Bestanden

```
├── dashboard.html          # Het interactieve web-dashboard (standalone)
├── data/
│   └── exameneisen.json    # Gestructureerde JSON met alle exameneisen
├── db/
│   └── schema.sql           # SQL database schema (MySQL/PostgreSQL)
└── README.md                # Dit bestand
```

## Gebruik

### Dashboard (standalone)
Open `dashboard.html` in een browser. Het dashboard werkt zonder server of internetverbinding.

**Features:**
- Selecteer band/slip → zie exameneisen
- Toggle: "Alles" vs "Nieuw voor deze band"
- Technieknamen aan/uit zetten
- Nederlandse vertalingen aan/uit zetten
- Direct inzien wat er bij elk examen hoort

### JSON Data
`data/exameneisen.json` bevat de volledige gestructureerde dataset:
- 11 band/slip niveaus (wit t/m bruin)
- 11 techniek-categorieën
- Per band: vereiste aantallen per categorie + nage-komi + kanteltechnieken + ukemi

### Database Schema
`db/schema.sql` bevat het relationele schema voor toekomstige uitbreidingen:
- `belt_levels` - Banden en slips
- `technique_categories` - Categorieën (ashi-waza, koshi-waza, etc.)
- `techniques` - Individuele technieken met namen
- `belt_category_requirements` - Aantallen per band/categorie
- `belt_general_requirements` - Nage-komi, kantel, ukemi per band
- `belt_technique_assignments` - Expliciete koppeling techniek → band

## Toekomstige uitbreidingen

- [ ] Video-links per techniek
- [ ] Beschrijvingen per techniek
- [ ] Backend API met database
- [ ] Login-systeem voor trainers
- [ ] Examenplanning integratie
- [ ] Automatische voortgangsrapportage

## Credits

Gegevens gestructureerd door Kimi K2.6, gebaseerd op exameneisen van Judoclub Michigami Steenbergen.
