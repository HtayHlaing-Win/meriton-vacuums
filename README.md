# 🏢 Meriton Vacuums — Pantry Vacuum Tracker

A real-time shared web app for house attendants to track vacuum cleaner inventory across pantries on **Levels 4 to 29**.

-----

## 📱 Features

- **Live sync** — updates every 3 seconds across all devices
- **Shared by all staff** — any change is instantly visible to the whole team
- **Per floor tracking** — mark each pantry as Has Vacuum / Missing / Not Checked
- **Quantity counter** — track how many vacuums are on each floor
- **⚠️ Excess alert** — floors with more than 1 vacuum are flagged amber and sorted to the top
- **Search by floor** — type a floor number to jump straight to it
- **Notes** — add a note to any floor (e.g. “vacuum broken”, “borrowed to L12”)
- **QR code** — scan to open the tracker on any phone
- **Works on all phones** — mobile-first design, dark mode supported

-----

## 🚀 How to Use

1. Open the link on your phone
1. Type a floor number to search, or scroll through the list
1. Tap a floor card to expand it
1. Select **Yes, has one** or **No vacuum**
1. Use **+** / **−** to set the exact quantity
1. Add a note if needed
1. Changes save instantly and sync to all other phones

-----

## 🛠️ Tech Stack

|Layer   |Tool                                           |
|--------|-----------------------------------------------|
|Frontend|HTML, CSS, JavaScript                          |
|Database|[Supabase](https://supabase.com) (free tier)   |
|Hosting |[GitHub Pages](https://pages.github.com) (free)|

-----

## 🗄️ Database Setup (Supabase)

Run this in your Supabase SQL Editor to set up the table:

```sql
create table floors (
  floor int primary key,
  status text default 'unknown',
  qty int default 0,
  note text default ''
);

insert into floors (floor)
select generate_series(4, 29);

grant select, insert, update, delete on table floors to anon;
```

-----

## 📦 Deployment

1. Push `index.html` to this repository
1. Go to **Settings → Pages → Branch: main → Save**
1. Your live URL: `https://YOUR-USERNAME.github.io/meriton-vacuums`

-----

## 👷 Built for

Meriton housekeeping team — internal use only.