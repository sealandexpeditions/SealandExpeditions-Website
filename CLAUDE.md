# SeaLand Expeditions website

Website for SeaLand Expeditions, a Belizean-owned tour company in Belmopan, Cayo. Plain static HTML, no backend, no build step.

## Pages
index.html (home), about.html, tours.html, gallery.html, booking.html, faq.html, contact.html.
Every page repeats the same top bar, navigation, and footer. If you change the nav or footer, change it on all 7 pages.

## Hosting
- Code lives in this GitHub repo (sealandexpeditions/SealandExpeditions-Website), `main` branch.
- Render hosts it as a free Static Site at https://sealandexpeditions-website.onrender.com and auto-deploys on every push to `main`.
- Everything must stay free. Do not add paid services, databases, or server code. Do not add a build step.

## Styling
- Tailwind loads from this exact line in every page's head. Keep it exactly:
  <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
- Brand colors and fonts are defined in the `<style type="text/tailwindcss">` block in each page's head: jungle (dark green), leaf (green), river (blue), Source Serif 4 headings, Source Sans 3 body.
- Design phone-first and check narrow screens.

## Forms (do not break)
- booking.html and contact.html post to Web3Forms: `action="https://api.web3forms.com/submit"` with `method="POST"`. Never change it to `https://web3forms.com` (that returns a 405 error).
- Keep the hidden `access_key` input, `subject`, `from_name`, and `botcheck` inputs.
- Booking form field names: name, email, tour_type, preferred_date, guests_count, message. Contact form: name, email, phone, message.
- The small script at the bottom of each form page submits in the background and shows a thank-you message. Keep it.
- booking.html reads `?tour=` from the URL to preselect a tour. The option text must match the tour name exactly.

## Images (important)
- Images currently load from https://sealandexpeditions.com/wp-content/uploads/2023/11/ (the old WordPress site).
- Before the WordPress site is turned off or the domain is moved, download those images into an `images/` folder in this repo and change every image URL to `images/<filename>`. Otherwise every photo will break.
- Compress new photos before adding them.

## Working rules
- Write every URL out in full; never shorten links.
- New pages are .html files in the repo root, linked with relative links, with the same nav and footer.
- Keep wording on tours, prices, and FAQs accurate. Ask before inventing facts, prices, or tour details.
