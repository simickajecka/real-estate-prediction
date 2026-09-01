# real-estate-prediction

Superproject for a Serbian real-estate price-prediction system: collection from
the two largest portals, a typed and deduplicated data layer, and the price
models built on top of it.

```
real-estate-prediction/
├── data-prep/                    collection · contract · typed storage
│   ├── llm-benchmark/            the schema contract (rule_cards_tree.json)
│   ├── listings-harvest/         scrapers: halooglasi + nekretnine.rs
│   └── listings-data-layer/      typed storage, dedup, Parquet export
└── modeling/                     price models
    ├── real-estate-pricing/      CatBoost - rent (built), flat-sale, house-sale
    └── tabfm/                    TabFM in-context benchmark
```

The two layers meet at one artifact: `data-prep` produces `listings.parquet`,
`modeling` consumes it. Models never touch scrapers or live databases.

## Clone

```bash
git clone --recurse-submodules https://github.com/simickajecka/real-estate-prediction.git
```

Already cloned:

```bash
git submodule update --init --recursive
```

Pull everything, submodules included:

```bash
git pull --recurse-submodules && git submodule update --init --recursive
```

Bump every submodule to its remote tip:

```bash
git submodule update --remote --recursive
```
