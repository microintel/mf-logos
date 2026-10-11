# MF Logos — MicroIntel

A public directory of mutual fund logos with searchable HTML index and reusable JSON files.

## Files
- `index.html` — searchable logo directory; deploy with GitHub Pages.
- `service.json` — service metadata and `funds` array (`name`, `url`).
- `mf-logos.json` — simple array of `{ "name", "url" }` entries.
- `images/` — logo image files.

## Public JSON URLs
After pushing to the `main` branch:
- Service JSON: `https://raw.githubusercontent.com/microintel/mf-logos/main/service.json`
- Simple array: `https://raw.githubusercontent.com/microintel/mf-logos/main/mf-logos.json`
- GitHub Pages index (after enabling Pages): `https://microintel.github.io/mf-logos/`

## JSON structure
`service.json`:
```json
{
  "name": "MicroIntel Mutual Fund Logos",
  "version": "1.0.0",
  "count": 53,
  "funds": [
    {
      "name": "360 ONE Mutual Fund",
      "url": "https://raw.githubusercontent.com/microintel/mf-logos/main/images/360-one-mutual-fund.png"
    }
  ]
}
```

## Use it in JavaScript
```js
fetch("https://raw.githubusercontent.com/microintel/mf-logos/main/service.json")
  .then(response => {
    if (!response.ok) throw new Error("Failed to load MF logos");
    return response.json();
  })
  .then(data => {
    console.log(data.funds);
  });
```

## Enable GitHub Pages
1. Push these files to the `main` branch of `microintel/mf-logos`.
2. Open repository **Settings → Pages**.
3. Under Build and deployment, choose **Deploy from a branch**.
4. Select branch `main` and folder `/(root)`, then Save.
5. Wait for the deployment, then open `https://microintel.github.io/mf-logos/`.

Note: `service.json` and `mf-logos.json` are served directly from GitHub Raw even without Pages; the searchable `index.html` needs Pages (or a local web server) to run as a website. Logo URL paths are based on the current `main` branch.
