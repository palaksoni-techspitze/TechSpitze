# TechSpitze — Product Requirements & Handoff

## Original problem statement
Build a static, frontend-only marketing website (no backend, no database, no auth needed) for TechSpitze, a Canadian IT consulting company. Dark navy glassmorphism design, 4 pages, all in one build.

Design: #060a16 background, #0b1120 / #141c33 elevated surfaces, #eef1fb headings, #a3adca body, #4fd8c4 teal accents, #e7b158 gold CTAs. Translucent glass cards/nav with borders, blur and soft shadows; subtle teal/gold background orbs. Syne headings, DM Sans UI. Pill buttons. Sticky shared TS navbar and comprehensive footer. CSS/inline SVG visuals only; no generated imagery.

Home: “Lead the Future of Your Industry”; supplied subheading; Get Started/Explore Services; 5 countries, 4 pillars, 60+ partners; illustrative live engagement panel; audience chips; four service cards and all specified bullets; three value props; technology ecosystem; five office cards; closing CTA.

Services: “Enterprise Services Built Around Outcomes”; four full-width detailed glass service panels covering AI & Automation, Enterprise IT, Development, Marketing & Branding; audience-specific engagement models; closing CTA.

About: “Your Trusted Partner in Enterprise Excellence”; mission connecting R&D leadership and delivery; exact results-not-promises quote; three principles (AI-first always, Platform-agnostic, Accountable delivery); audience chips; global stats; closing CTA.

Contact: “Let's Build What's Next”; full name, work email, company, 5-option interest selector, message and Send Message; inline success only, no sending/storage. Full supplied addresses for Victoria BC (HQ), Alamance NC, Dubai, Ahmedabad, Dublin.

User confirmed: “Yes, build as specified (Recommended): Use the provided design, content, and frontend-only contact form.”

Additional requested art direction: award-worthy distinctive cohesive experience, large kinetic hero and masked line-by-line reveal, numbered manifesto chapters, one slow editorial marquee, Framer Motion scroll/micro-interactions, Lenis momentum scrolling and a subtle 3D/parallax hero. Original SVG-only imagery constraint retained following confirmation of the specification.

## Architecture
- React 19 frontend with React Router for /, /services, /about, /contact and 404 fallback.
- No backend requests, database, authentication, integrations, or uploads. Existing backend template is unused.
- Shared content module for services, offices, segments, values and principles.
- Components: Shared, Layout, OrbitalScene, Cityscape, HomeSections, ContactForm. Pages are separate modules.
- Shadcn Button, Input, Textarea and Select. Lucide inline SVG icons.
- Framer Motion for masked headings, section reveals and spring-based cursor parallax. Lenis smooth scrolling, hash routing, reduced-motion support.
- Custom mathematically projected SVG torus; hand-drawn inline SVG city skylines.
- Form validated locally; no submission requests or persistence; confirmation explicitly clarifies no message was sent/stored.

## Implemented
- All four responsive pages, shared sticky glass navigation/mobile disclosure and footer.
- Active navigation, page titles, 404, skip link, keyboard focus, mobile Escape dismissal.
- Complete supplied service descriptions, five office addresses and genuine external map links.
- Service anchor navigation and interest preselection from /contact?service=service-id.
- Contact required-field validation, inline errors, success state and reset.
- Office-local clocks, ecosystem marquee, hover states, reduced-motion preferences.
- Brand favicon, description/Open Graph metadata and Google Fonts.
- Production build compiled successfully; visual desktop checks on Home, Services and Contact passed.

## Prioritized backlog
- P0: No missing core features. Complete comprehensive browser QA, fix findings.
- P1: Optional future real message delivery, only if user requests integration beyond static scope.
- P2: Verified client case studies / testimonials supplied by the company to improve contact conversion.

## Official website content update
User request: “Use content and Logo from this website - https://www.techspitze.com/” plus attached official logo.

Retrieved the homepage, About, Contact, GenAI & Automation, Cloud Services and Digital Marketing pages. Parsed published footer service catalog and addresses. Curation excludes source-site lorem ipsum, duplicated template blocks and irrelevant placeholder sections.

- Official supplied transparent blue/grey logo is now used unaltered in navbar/footer: `/brand/techspitze-logo.webp` (source: user attachment).
- Official site icon in favicon, Apple touch icon and About orbital graphic: `/brand/techspitze-mark.png`.
- Published mission, vision, four core values (Ethics, Collaboration, Innovation, Customer Satisfaction), R&D copy and founder message from Ravi Soni used on About.
- Founder portrait sourced from official About page, locally bundled at `/brand/ravi-soni.png`.
- Four original service pillars preserved, with source-based descriptions and accessible expandable full capability catalogs: AI; Managed IT/Cybersecurity/Cloud/Data/IT Consulting; Web/Mobile/Software; Digital Marketing/Branding.
- Official full addresses include Victoria V8Z 3G4, Alamance 27215, Dubai street number 106, Ahmedabad Sindhubhavan Rd/Thaltej/Gujarat 380059, and Dublin D01 TX31.
- Footer legal entity updated to TechSpitze IT Solutions & Consulting LTD; contact copy reflects “Data. Insights. Decisions. Outcomes.” and “Your journey. Our partnership.”
- Added Brand.css and ServiceCapabilities.jsx. Kept navy/teal/gold design with original blue logo untouched.
- New website request supersedes the original custom TS logo. Genuine brand assets / published founder photograph used; no generated imagery.

Sources:
- https://www.techspitze.com/
- https://www.techspitze.com/about/
- https://www.techspitze.com/contact/
- https://www.techspitze.com/what-we-do/genai-automation/
- https://www.techspitze.com/what-we-do/cloud-services/
- https://www.techspitze.com/what-we-do/digital-marketing-services/

## Our Team page addition
User request: “https://www.techspitze.com/our-team/ Make our team page for my website with this content and photos”.

- Added `/our-team` and `/our-team/` route (React Router trailing-slash matching), title, desktop/mobile/footer navigation, and About → Meet our team link.
- Team content extracted from official HTML and published portrait URLs; 19 visible public profiles downloaded to `/public/team/`.
- Two founder spotlights (Ravi Soni, Achal Shukla), eight leadership portraits, nine operations/delivery profiles. Original photo-person pairings preserved.
- Paresh Shah is explicitly `display:none` on source, so omitted rather than exposing a profile the source intentionally hides.
- Only source-provided roles are shown. Lauren Nackmen, Timi Bialose, May Thin Cho, and Kalpak Pathak have no published roles; none invented. Achal's truncated source bio is reduced to the complete, confirmed sentence about his CFO/co-founder position.
- Minor source typo corrections: Operations & Delivery, Chief Legal Officer; Ali Asgar Pancha restored from the official image filename (visible heading drops initial A).
- Source photos preserve original aspect ratios and full framing. Founder photos 699×439; other portraits 340×426. Lazy loading for nonfounder portraits.
- Premium numbered chapter layout, Framer Motion reveals, portrait hover treatments, original company core values and closing contact CTA.
- New files: data/team.js, pages/Team.jsx, Team.css. No backend or new integrations.

## Professional black / blue / white theme
User request: “Make the fonts bigger a bit and chnage the theme colour in Black, blue and white theme. Make its professional and bold”.
- Added ProfessionalTheme.css as cohesive final palette/type layer: near-black #050609, blue #6193ff accents, white headings, blue CTA buttons, larger nav/body/card/footer/form typography and bolder headings across all five pages.
- Orbital artwork gradients changed from teal/gold to blue/white. Official blue logo and authentic portraits remain unaltered.
- Mobile type scales adjusted to reflow without clipping.

## Dropdown header and animated map
User request: “Make the header with a dropdown and in Chnages services to what we do and have a drop down with Gen AI & Automation Cloud Services Branding services Cybersecurity Services Data Anyalytics Digital Marketing. CHnage Abot to Who we are and drop down to About Our Team Blog Case Study. Make the Heade background Black. For the location show it on Map with nice animation for different locations”.
User choice: “Use the existing TechSpitze website pages (Recommended): Keep this build focused on the new navigation and animated location map.”

- Solid black header. Desktop Radix/Shadcn navigation menus: Home, What we do (six services), Who we are (four pages), Contact; Let's Talk CTA retained.
- Mobile expandable submenus with scrolling for short screens and keyboard Escape support.
- Blog and Case Study point to verified HTTP 200 official external URLs, opened safely in a new tab: https://www.techspitze.com/blog/ and https://www.techspitze.com/case-study/.
- Direct links to specific service groups automatically expand the relevant capability accordion and scroll to the group.
- Added country-outline world map to Home/global footprint and Contact. Static world-atlas TopoJSON + d3-geo + topojson-client; no map API, credentials or backend.
- Five geolocated offices, animated connection paths, selected-country highlighting, pulsing markers, manual city selection, previous/next controls, pause/play automatic location tour, synchronized address panel and external Google Maps links.
- Pointer/focus pauses the tour, manual selection stops it; respects reduced motion. SVG markers keyboard-accessible, office buttons available at all widths.
- New components HeaderNavigation, LocationsMap, WorldMapGraphic; data/navigation.js; NavigationMap.css.

## Content reduction and breathing room
User request: “Kepp it less content and have some breathing space in the website”.
- Home now has a short three-part hero statement, one-sentence service cards instead of repeated bullet lists, compact value props, fewer decorative labels, and cleaner section headings.
- Service descriptions and engagement-model copy shortened; complete service catalogs still accessible through expandable sections and dropdown deep links.
- About keeps mission, core values, quote, principles, and footprint. Vision/R&D approach moved into an accessible expandable section. Removed repeated founder block and audience chips; founder portraits remain on Team.
- Team retains all 19 public profiles but removes repeated explanations/value band and simplifies section headings.
- Contact now prioritizes the form, a short global-team aside, and one animated map. Removed duplicate five-office address cards; full official addresses and map links remain available through location selection. Footer /contact#office links map to anchors above the map and preselect the correct office.
- QuietLayout.css provides more section/card/grid spacing while preserving readable type and mobile reflow. Navbar dropdown copy pared back.
- No functionality removed from navigation, maps, contact validation, or team directory.

## Metrics, customer videos, localization and typography updates
Latest requests: professional animated statistics with centrally editable factual values; multiple 20–30 second customer video testimonials with posters/play/lightbox; consistent city/region/country labels; exact marketing statement; repair English/French/Hindi switching; make the entire site's fonts bold and presentable. Preserve existing design and spacing.

- Central metrics configuration `src/data/metrics.js` controls impact, hero and About counters. Defaults derive 19 people / 11 specialist practices / 5 offices from published data, with 4 pillars and 60+ partners from prior brief. Customer/project/SLA/experience/support entries remain null/unpublished without verified company data. If enabled, nulls show an explicit awaiting-verification label.
- Sliding digit animation uses Framer Motion once on viewport entry, with reduced-motion bypass and screen-reader numeric labels.
- Statistics heading exactly “Measurable Results. Real Business Impact.” and requested supporting sentence.
- Testimonial configuration `src/data/testimonials.js`; no real clips supplied. Visible neutral pending-content state. Component accepts multiple real entries with names/company/country/title/poster/video/optional logo/captions/duration. Direct HTTPS MP4/WebM or build-time media assets supported. Lazy posters, no video request until modal open, native video controls, no autoplay, Escape/focus behavior, close unmounts playback. No fake customer endorsements.
- Locations extracted to `src/data/locations.js`; Victoria BC Canada, Alamance NC USA, Dubai UAE, Ahmedabad Gujarat India, Dublin County Dublin Ireland. Footer/maps/tabs/labels reuse directory. Australia omitted pending confirmed address.
- Exact marketing statement is centralized and reused on About/footer/metadata: “Tailored solutions built around your business, designed to deliver measurable value.”
- LocaleProvider + bundled EN/FR/HI catalogs; persistent selector on desktop/mobile. Document language, navigation, pages, forms/errors/confirmation, service catalogs, footer, metrics and maps localized. Proper names, technology brands, addresses and user input stay unchanged. Fixed React translation traversal preserving single-child elements for Radix asChild, eliminating a blank-page runtime error.
- New sitewide Typography.css: bold Manrope headings and Plus Jakarta Sans body/UI; Noto Sans Devanagari for Hindi. Existing black/blue/white design preserved.
- Editing guide: `/app/frontend/CONTENT_GUIDE.md`.
- Public screenshots confirmed homepage, French and Hindi Contact rendering, metrics and testimonial pending state. Production compilation passes. Full independent QA remains pending; do not claim localization bug verified until testing agent report passes.

## Home marketing copy replacement
Latest request: Replace “Customized IT solutions that deliver real value for businesses.” with exactly “Tailored solutions built around your business, designed to deliver measurable value.” on Home.
- Home hero now reads `company.marketingStatement`, the same exact centralized sentence as the footer, About mission and metadata. One responsive element is used at all screen sizes; no separate mobile copy.
- Removed the obsolete old mission sentence from the unused translation catalog. French/Hindi use the matching localized statement.

## Next tasks
Run frontend-only testing of all changes, especially dropdowns (desktop/mobile/keyboard), six service anchor destinations, external links, maps and pause/play/selection, responsive typography, team portraits, About accordion, form validation/success/reset, and reduced motion. Review final report and resolve defects.