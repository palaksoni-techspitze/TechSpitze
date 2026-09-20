# TechSpitze content configuration

The site remains a static React website. No database, login, upload form, or messaging backend has been added.

## Metrics: `src/data/metrics.js`

All metric values, labels, visibility lists, and their provenance live here.

- `metricsConfig.impactKeys` chooses the large statistics shown on Home.
- `heroKeys` and `aboutKeys` choose the smaller statistics.
- Existing public facts: 5 countries/offices, 4 service pillars, 60+ technology partners (original company brief), 19 published team profiles and 11 published specialist practice groups.
- Customer counts, projects, SLA and years of experience are **not verified**. Their entries have `value: null` and are not published by default.
- If an unverified entry is added to `impactKeys`, it shows an em dash and “Awaiting verified company figures”, never a fabricated number.
- To publish a verified metric, enter its numeric value, optional suffix, source, and set `placeholder: false`. The rolling digits also support decimals and formatted strings such as `1,000+`, `99.9%` and `24/7`; only publish confirmed commitments.
- Animation runs once when entering view and is skipped for reduced-motion preferences.

## Customer videos: `src/data/testimonials.js`

The live testimonial list is empty until real, approved customer clips are supplied. A neutral “coming soon” panel explains that no testimonials have been published; it contains no invented customer or endorsement. Set `testimonialsConfig.showEmptyState` to false to hide the panel until clips are ready.

Add one object per approved video:

```js
{
  id: 'unique-short-id',
  name: 'Actual customer name',
  company: 'Actual company name',
  country: 'Canada',
  title: 'Approved customer quote or video title',
  videoUrl: 'https://your-media-host.example/customer-approved-video.mp4',
  posterUrl: 'https://your-media-host.example/customer-approved-poster.jpg',
  durationSeconds: 25,
  companyLogoUrl: undefined, // optional
  captionsUrl: undefined, // optional public .vtt file
  captionLanguage: 'en'
}
```

- Direct HTTPS MP4/WebM URLs and build-time asset paths such as `/media/approved-video.mp4` are supported. External watch-page URLs are not direct media URLs.
- Prefer a durable object-storage/CDN URL for uploaded customer media. There is no runtime local-file upload/storage feature.
- Use real 20–30 second clips, H.264 MP4 for broad support, a compressed poster, and WebVTT captions where possible.
- No video media is loaded until the customer clicks a poster. The lightbox provides native controls, no autoplay, keyboard Escape, focus restoration, and stops/unmounts playback when closed.
- Customer names, company names, quotes, logos and video content are never silently translated. Surrounding controls, country labels, headings and errors are localized.
- Multiple entries automatically form a responsive grid.

## Locations: `src/data/locations.js`

The footer, maps, map markers, address panel, Contact country summary and location-based metrics use this canonical directory. `officeLocality()` produces city + region; `formatLocation()` adds the country label.

Confirmed display labels:
- Victoria, BC, Canada
- Alamance, NC, USA
- Dubai, UAE
- Ahmedabad, Gujarat, India
- Dublin, County Dublin, Ireland

Australia is deliberately not listed without confirmed city, state and office address. Add a verified location with its country ISO code, numeric world-atlas country ID, address, coordinates, latitude/longitude, timezone and label offset when details are available.

## Marketing statement

`company.marketingStatement` in `src/data/content.js` is exactly:

“Tailored solutions built around your business, designed to deliver measurable value.”

The About mission, footer and localized metadata use it. English HTML metadata has the same default for crawlers.

## Languages: `src/i18n/`

- English is the default. French and Hindi dictionaries are bundled locally; there is no runtime translation API.
- Catalog rows are `[English source, French, Hindi]` in UI, service, content and update dictionaries.
- `LocaleProvider` persists `techspitze-language` in localStorage, sets the document language and translates React content before render while retaining element refs, keys, IDs and single-child shapes.
- `L` wraps rendered copy; `useLocale().t()` handles dynamic/accessible labels and metadata.
- Use `translate="no"` for user input, proper names, company names, postal addresses and approved customer quotes. URLs and data values are never translated.
- Additional languages need an entry in `languages`, a catalog column/map and a font when required. There are no duplicate page implementations.
- External Blog/Case Study pages retain the official external website's language behavior.