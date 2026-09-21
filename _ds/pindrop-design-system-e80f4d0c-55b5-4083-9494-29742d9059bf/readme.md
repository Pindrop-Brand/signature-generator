# Pindrop Design System

Pindrop builds voice/audio security and fraud-detection technology for contact centers and enterprises — deepfake and synthetic-voice detection, caller authentication, risk scoring, and call analysis. This design system was assembled from a single mounted Figma file, **"CLAUDE TRAINING FILE.fig"**, which functions as Pindrop's brand + product component library (not a live codebase — no GitHub repo was attached).

Figma pages used: `/WIP-guidelines` (brand guideline frames — color, type, logo, voice), `/Final-logos` (approved logo lockups), `/Website-examples`, `/Ads`, `/Photo-Library`, `/Fractals-background-texture`, `/Cover`. Component families and design tokens live throughout the file; see `/METADATA.md` in the source for the full inventory.

Uploaded assets: Geist + Geist Mono variable font files, and finished Pindrop logo/mark SVGs (orange, black, white).

## Index

- `styles.css` — root stylesheet, imports everything below
- `tokens/` — `fonts.css` (@font-face), `fig-tokens.css` (509 tokens from Figma Variables: primitives, semantic aliases, component tokens, theme scopes), `type-scale.css`, `spacing.css`
- `assets/fonts/` — Geist + Geist Mono TTFs · `assets/logos/` — logo & mark SVGs (orange/black/white)
- `guidelines/` — foundation specimen cards (color, type, spacing, radius/shadow, logo lockups)
- `components/` — reusable UI primitives, grouped by concern (below)
- `SKILL.md` — portable skill file for using this system in Claude Code

## Components

Extracted from the Figma file's component library (146 component sets + 46 standalone symbols = 177 families total). **153 of 177 families are built** — see "Coverage" below for what's outstanding.

- **forms/** — Button, Input, Checkbox, V2Checkbox, TextDropDown, AtomInput, AtomLabel, AtomFeedback, ErrorMessageV2, Base6, BaseV2, BaseDropdownOptions, BaseOptionItem
- **feedback/** — Lozenge, Banner, Disclaimer, AtomMessagesProgressBar
- **data-display/** — Avatar, Presence, PresenceBadge, Cell, TextLabelPair, Person, FillFalseIconSquare, FillTrueIconSortVertical
- **navigation/** — AtomsNavigationMainNav, AtomsNavigationMainNavBase, NavigationTab, NavItem, Pagination, TabsRegular, TabsCases, AtomTabsRegular, AtomTabsCases2, List, Sitemap, Charts, Cubes, Folder, Phone, Settings, PeopleDEPRECATEDUseUser
- **icons/** — Arrow, Chevron, Close, Check, Warning, Minus, Refresh, Info, Help (canonical single-color icon set, ~15 glyphs in the source)
- **media-objects/** — Building, User, Bot, Camera, Document, LocationPin
- **audio/** — AudioControls, Waveform, Microphone, Volume
- **risk-analysis/** (Pindrop's domain-specific product components) — RiskRatingV1, RiskRatingHighRisk, GaugeProgress, BsseGaugeProgress, CallList, BaseAnalysisChip, BaseDeepfakeAnalysisResult, BaseVoiceSimilarityResult, BaseLocation, BaseLocationRisk, BaseConsentStatus, SecondaryScore, NewScore, Chat, Robot, User2, Warning2, Warning3, Check2, IconsChevron
- **product-ui/** — Table, Column1x4, Header, AtomNavHeader, Breadcrumbs, Search, Metrics, ReportCard, HistoryCard, BaseHistoryCard2, Article, CopyPaste, Trash, PlayButton, Player, Image, ImagePlaceholder, ImagePlaceholder24px, Logo, Logo2, TagEngineContentType, DropDown, Calls, CallsCallListItem, CAAvatar, CAParticipantCard, RelatedCallsTable, RelatedArticles, IconsClose, Lozenge2, V2Checkbox2, PINDROPWebButtonInteraction2, BaseAnalysisChip2
- **branding/** — PindropLogo, PindropLogoMark
- **assets/fractals/** — FractalMirroredPattern5 (exact source fractal texture, extracted from the Figma file's Fractals-background-texture page)
- **misc/** — BaseAudioButtonsNew, BaseAudioPlayerNew, AudioControls2, AtomTabsCases, BaseSm01, BaseSm02, BaseSm03, BaseSm04, BaseSm05, BaseSm06, BaseRelatedCallsResult, ArrowCircle, PINDROPWebShareButton, PINDROPWebButtonInteraction, IconFacebook24px, AtomsNavigationSubnavBase, CABottom, CAHead, AtomGaugeProgressNew, ImagesPlaceholderAlt01, Article3, ColorCardRed, Header1160Grid, HeaderActionsMeetingDuration, NavItem2, RiskRatingLowRisk, RiskRatingModerateRisk, Tag, Video, NavigationFooterDesktop, PINDROPWebButtonInteractionOn, PINDROPWebButtonInteractionPrimary, PINDROPWebButtonInteractionSecondary, Item, AtomsNavigationSubnav, IconFacebook24pxAlt, IconCheckCircleSmall24px

### Coverage

153 of 177 Figma component families are built. Not built (24 families, all intentional skips): Zoom/meeting-app chrome mockups (Traffic Lights, Window Base/Header, Toolbar Status/Recording, Zoom Apps gallery/side-by-side bars, Zoom Meeting browser header), a deprecated variant (People DEPRECATED), a large composite that exceeds the extractor's size limit (Footer + CTA), and exact duplicates already covered by canonical components under a different Figma path (Icons/Check, Icons/Minus, Icons/Warning duplicate icons/Check-Minus-Warning; Scores/Call List duplicates CallList; 01 Images/Placeholder Alt. duplicates ImagesPlaceholderAlt01; Parent Component and Primary Colors are internal Figma helper/reference frames, not UI). None of these affect the primitives a product screen needs.

### Intentional additions

None beyond what the source defines — every component above maps to a named Figma component family. `ImagePlaceholder24px` is a renamed extraction artifact (was a nested Figma instance with no clean top-level name); it corresponds to the source's "24px / image placeholder" component. `IconFacebook24px` is likewise renamed from the source's "24px / Facebook" standalone icon. `ImagesPlaceholderAlt01` is renamed from the source's "01 Images / Placeholder Alt." component (the literal name isn't valid as an export identifier). `IconFacebook24pxAlt` and `IconCheckCircleSmall24px` are renamed from a second "24px / Facebook" instance and "24px / check circle small" respectively — same reasoning. `FractalMirroredPattern5` is not a component family — it's the exact "fractal-mirrored pattern 5" frame from the Fractals-background-texture page, extracted at the user's request as a graphic-element asset, not a UI primitive.

## Content fundamentals

- **Voice**: confident, technical-but-clear. Pindrop writes like the people who build detection systems — precise nouns (signal, detection, verification, risk), short declarative sentences, no hype adjectives. From the brand guidelines: *"Geist and Geist Mono create a typography system that feels modern, highly legible, and engineered for digital consistency."*
- **Tone**: trust and precision over friendliness. Copy explains what the system does (detects, verifies, flags) rather than how the user should feel.
- **Casing**: sentence case for UI copy and headings; Geist Mono labels (call IDs, scores, timestamps, system states) run in UPPERCASE for a technical/instrumentation feel.
- **Second person is rare** — product copy mostly describes the system in third person ("the logomark can be used independently...") rather than "you."
- **No emoji** anywhere in the source material — the visual language of trust/security skews serious.
- **Numbers as evidence**: risk scores, percentages, and confidence values appear directly in UI copy (mono type) as the core content, not decoration — this is a data-forward, evidence-driven product.

## Visual foundations

- **Color**: this system designs against **semantic tokens only** — `background-primary/secondary/tertiary/inverse`, `border-default/strong/subtle`, `core-background-*`, `accent-{orange,cyan,green}-{subtle,muted,default,emphasis}`, plus component-level tokens (`component-button-*`, `component-tag-*`). Raw primitive/scale values (`--orange-500`, `--neutral-white`, etc.) exist only inside `tokens/fig-tokens.css` as internal aliases the semantic tokens point to — never reference a primitive directly in a component or design. The brand's primary palette (confirmed by the user): signal orange `#FF5100`, lime `#F0FF91`, cyan `#B0E7EB`, ink `#140700`, white `#FFFFFF`, off-white `#F2F0EB` — these six anchor the semantic tokens above and appear on the `guidelines/colors-primary-brand.html` card. A secondary scale extends orange, lime/olive, and cyan/teal into 5-step tint→shade ramps plus a warm-neutral ramp (`guidelines/colors-secondary-scale.html`) — used for tints, hover/emphasis states, and status variants layered on the semantic tokens. Brand gradients (`guidelines/gradients.html`) blend lime→orange→brown and lime→cyan diagonally — reserved for brand/marketing moments, not product UI.
- **Type**: Geist (sans) for all UI, headings, and body copy — set with tight negative tracking (-0.05em) at display sizes, easing to normal tracking at body sizes. Geist Mono for data, labels, system/technical copy, often uppercase with +0.02em tracking — "referencing code, detection systems, and machine analysis to reinforce the brand's connection to AI and signal verification" per the brand guidelines.
- **Logo**: a directional flag-like signal mark plus a wordmark, in orange/black/white. "The Pindrop logo is built around a directional signal mark and a confident wordmark... express[ing] detection, movement, and precision."
- **Spacing**: a numeric 4px-based scale (4/8/12/16/20/24/32/40/48/56/64) — used consistently for gaps and padding across components, no half-steps.
- **Corner radii**: small (6px) on controls/chips, medium (10px) on cards/inputs, large (16px) on panels, full/pill for lozenges, tags, and status badges.
- **Shadows**: soft, low-contrast elevation only — `0 1px 2px rgba(20,7,0,.04)` for subtle lift, up to `0 8px 24px rgba(20,7,0,.08)` for panels/modals. No heavy or colored shadows.
- **Cards**: white or off-white surface, medium radius, 1px neutral border or a soft shadow (rarely both heavily), generous internal padding on the 8px scale.
- **Backgrounds**: mostly flat off-white or white; the file also includes a separate fractal/generative texture library (`/Fractals-background-texture`) for full-bleed marketing/brand moments — not used in product UI.
- **Imagery**: a dedicated photo library page exists in the source; product screens themselves lean on data visualization (waveforms, gauges, risk charts) rather than photography.
- **Borders**: thin (0.5–1px), low-contrast neutral, used to separate table rows/cells and outline inputs — not decorative colored borders.
- **Transparency/blur**: not a dominant motif in the source; overlays where present use solid neutral surfaces, not glass/blur effects.
- **Animation/hover/press**: not specified at the token level in the source file (Figma is static); component variants do define `hover`/`focus`/`selected`/`disabled` states for buttons and inputs — treat these as color/weight state changes (no motion spec was available to extract).

## Iconography

**All icons use Google Material Symbols (Outlined, weight 200)** — loaded via `tokens/icons.css` (`@import` from Google Fonts) and rendered as `<span class="material-symbols-outlined">` glyphs at `font-variation-settings: 'wght' 200`. `components/icons/` (Arrow, Check, Chevron, Close, Help, Info, Minus, Refresh, Warning) and the icon-like glyphs in `components/media-objects/` (Building, User, Bot, Camera, Document, LocationPin) and `components/audio/` (Microphone, Volume) all wrap Material Symbols glyphs as small React components with a `size` prop. This supersedes the Figma file's own custom vector icon set entirely — a deliberate override, not an extraction gap.

Composite audio/data widgets (Waveform, AudioControls, Avatar, Presence, gauges, etc.) remain sourced from the Figma file, since they're bespoke compositions rather than single icon glyphs.

Font Awesome 7 Pro is still referenced by several product-UI components (buttons, cells, nav) as an icon font from the source file; no license/webfont was provided for it, so those glyphs fall back to the browser default until a licensed file is supplied. No emoji or unicode-as-icon usage found in the source.

## Fonts

Geist and Geist Mono variable fonts were uploaded directly (`assets/fonts/`) and wired up in `tokens/fonts.css`. The source file also references DM Sans, DM Mono, Open Sans, Poppins, Inter, SF Pro, and Font Awesome — these were secondary/legacy or icon-font usages found in older frames; no files for them were provided, so their tokens point at the real family name with a generic fallback stack until real font files are supplied (do not substitute a different family).
