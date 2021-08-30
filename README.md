# Basic GH action for Akka builds

Akka GH Actions builds have the same repeating block:

```
  steps:
      - name: Checkout
        uses: actions/checkout@v2
        with:
          fetch-depth: 0

      - name: Set up JDK 8
        uses: olafurpg/setup-scala@v10
        with:
          java-version: adopt@1.8.0

      - name: Cache Coursier cache
        uses: coursier/cache-action@v6.2

```

Over and over and over. This extracts the common block and makes it reusable via [GH Actions composition](https://docs.github.com/en/actions/creating-actions/metadata-syntax-for-github-actions#runsstepsuses).
