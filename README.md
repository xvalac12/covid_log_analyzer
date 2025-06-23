# 🦠 COVID-19 Log Analyzer

This project contains a Bash script `corona` that analyzes CSV logs with data on infected individuals. It supports filtering records by date and gender and provides various statistics about the spread of COVID-19.

---

## 🔧 Usage

```bash
./corona [FILTERS] [COMMAND] [LOG_FILES]
```

### 📑 Filters

| Parameter | Description |
|----------|-------------|
| `-a DATETIME` | Show only records after the given date (inclusive) |
| `-b DATETIME` | Show only records before the given date (inclusive) |
| `-g GENDER`   | Show only records of the specified gender (`M` / `F`) |

> **Note:** The `-s` filter is defined but not yet implemented.

---

### 🧮 Commands

| Command | Description |
|---------|-------------|
| `infected` | Display total number of infected individuals |
| `gender`   | Display number of infected by gender |
| `age`      | Display number of infected by age |
| `daily`    | Display daily infection statistics |
| `monthly`  | Display monthly infection statistics |
| `yearly`   | Display yearly infection statistics |
| `merge`    | Merge multiple logs into one CSV file (header appears only at the top) |

---

## 💡 Examples

```bash
# Number of infections after January 1, 2021
./corona -a 2021-01-01 infected data1.csv

# Number of infected women in 2020
./corona -a 2020-01-01 -b 2020-12-31 -g F infected data.csv

# Merge multiple log files
./corona merge log1.csv log2.csv > merged.csv
```

---

## 📁 Input File Structure

CSV files must contain the following header:

```
id,datum,vek,pohlavi,kraj_nuts_kod,okres_lau_kod,nakaza_v_zahranici,nakaza_zeme_csu_kod,reportovano_khs
```

Each row represents one infected individual.

---

## 📎 Requirements

- Unix-like system with Bash interpreter
- Log files in CSV format

---

## 📘 License

This project is intended for educational purposes.
