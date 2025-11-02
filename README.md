# UsenetStreamer

UsenetStreamer is a Stremio addon that bridges Prowlarr and NZBDav. It searches Usenet indexers via Prowlarr, queues NZB downloads in NZBDav, and exposes the resulting media as Stremio streams.

## Features

- ID-aware search plans (IMDb/TMDB/TVDB) with automatic metadata enrichment.
- Parallel Prowlarr queries with deduplicated NZB aggregation.
- Direct WebDAV streaming from NZBDav (no local mounts required).
- Configurable via environment variables (see `.env.example`).
- Fallback failure clip when NZBDav cannot deliver media.

## Getting Started

1. Copy `.env.example` to `.env` and fill in your Prowlarr/NZBDav credentials and addon base URL.
2. Install dependencies:

   ```bash
   npm install
   ```

3. Start the addon:

   ```bash
   node server.js
   ```

4. Add `http(s)://<your-addon-host>/manifest.json` to Stremio.

Place a 256×256 icon at `assets/icon.png` so the manifest advertises a logo.

## Environment Variables

- `PROWLARR_URL`, `PROWLARR_API_KEY`
- `NZBDAV_URL`, `NZBDAV_API_KEY`, `NZBDAV_WEBDAV_URL`, `NZBDAV_WEBDAV_USER`, `NZBDAV_WEBDAV_PASS`
- `ADDON_BASE_URL`

See `.env.example` for the authoritative list.

## License

This project is distributed under the ISC license (see `package.json`).