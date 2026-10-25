# Seinfeld episode drop

Use when writing an original, never-aired Seinfeld episode idea (the daily drop or one on demand), including rendering a scene script as a screenplay PDF and image.

Write one original Seinfeld episode idea as if the show never stopped airing.

## Pick the season and era
- Pick a season anywhere from the classic run through the 2000s, the 2010s, present day, or the near future. Rotate eras between drops.
- The season and year must line up. Season 1 is 1989 and Season 9 is 1998. If the show had continued, Season N would air in about 1989+N (Season 17 is 2006, Season 25 is 2014, Season 40 is 2029).
- Everything has to fit the era: technology, prices, slang, and the characters' jobs and life stages. For example, Elaine works at J. Peterman only from Season 8 on, there are no smartphones before about 2007, and the gang ages with the years.
- Head every drop with the title, season, and year, like **"The Title"**, Season N (YYYY).

## Holidays
- On Festivus (December 23), open with a funny, in-character Happy Festivus wish for the user (an airing of grievances, a feat of strength, the aluminum pole), and make that day's episode revolve around Festivus with a fresh premise, not the plot of the real Festivus episode.
- Around Christmas, Thanksgiving, New Year's, and other big holidays (Halloween, Valentine's Day, the Fourth of July, Hanukkah, and so on), make the episode about that holiday. Check today's date first.

## Format: alternate between the two
1. A logline plus A, B, and C plots (and a Kramer runner if it fits), then the last act where they collide.
2. A short partial script of one scene in proper screenplay format.

## Hard rules
1. Never reuse or echo the plot of a real Seinfeld episode. Check the core setups against the real 180 episodes, and replace the premise if there's a close match.
2. The last act must make logical sense: the plots collide through clear cause and effect that's set up earlier, not random chaos.
3. It's a show about nothing: petty social rules, small grudges, no hugging, no learning. Keep every character in voice. Invent new catchphrases and running bits rather than recycling famous quotes.
4. Don't explain the joke, don't write full-length scripts unless asked, and don't write other shows.
5. Don't repeat a premise. Log each drop in journal memory (title, season and year, format, and a one-line premise), and check the log first.

## Delivering a scene script
Send the script in a fenced code block in chat, AND attach a rendered PDF plus a PNG image of the script pages.
Also publish every scene script as a Page: a screenplay-style canvas of the scene. Always attach the PDF too, even when there's a Page.
Build on the box:
1. Write the scene as tagged lines, one per element: `S|` scene heading, `A|` action, `C|` character, `P|` parenthetical, `D|` dialogue.
2. Convert it to HTML with a short Python script. Use a Courier 12pt font and Letter pages with `@page { margin: 1in 1in 1in 1.5in }`. Add a centered title page (show name, the episode title in quotes, the season and year), followed by a page break. Use these left margins: character 2.2in in uppercase, parenthetical 1.6in, dialogue 1in at 3.5in wide. Action and scene headings are full width, and each element gets 12pt of space above it.
3. `google-chrome --headless --no-sandbox --disable-gpu --no-pdf-header-footer --print-to-pdf=Out.pdf page.html`
4. `pdftoppm -png -r 100 Out.pdf page` for the page images. Check one page visually before you send it.
5. Attach the PDF and the first script page's PNG (or all of the pages) after the code block. Out of character, keep it to a line or two.
