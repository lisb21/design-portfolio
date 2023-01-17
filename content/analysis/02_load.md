---
Title: load
--- 

Load
==========================

Uppgiften går ut på att undersöka tre sidors ladd-tider, hur effektivt dom svarar.

Urval
-----------------------

Urvalet är baserat på sidorna som användes i färganalys. Dom är intressanta här för att dom är uppbyggda på olika sätt. Det är även intressant att analysera samma sidor ur olika vinklar.


Metod
-----------------------
</br>

Verktyget som används är googles [pagespeed](https://pagespeed.web.dev/).
Genom detta kan man utvärdera olika krav google ställer för att öka chansen att sidan kommer upp i sökningar. Kraven är i stort basearde på hastigheter och optimering av ex bilder, javascript m.m. men även tillgänglighetsanpassning och hur lätt det är att katalogisera sidan på olika sätt (web-crawling).
[Länk](https://docs.google.com/spreadsheets/d/1cKgCTGfQp2UIUWircjpIHcOrBz9ZYBu8W6UWVcij4AI/edit?usp=sharing) till rådatan.

Resultat  
======================
</br>  
  
[Lynnandtonic](https://lynnandtonic.com/){.link-header}
-----------------------  

![lynnandtonic](image/lynnandtonicv2.jpg?width=300&height=300&q=70){.lynnandtonic}
</br>

Enbart en kommentar från google pagespeed, under Diagnostics "Avoid an excessive DOM size".
Inte så mycket att säga, har ingen egentlig förbättring att föreslå.

[Jävligtgott](https://javligtgott.se/){.link-header}
----------------------- 

![javligtgott](image/javligtgottv2.jpg?width=300&height=300&q=70){.javligtgott}

Kommentarer från google pagespeed:

- Opportunity
    - Serve images in next-gen formats
    - Reduce unused JavaScript
    - Eliminate render-blocking resources
    - Avoid serving legacy JavaScript to modern browsers  
- Diagnostics
    - Reduce the impact of third-party code
    - Does not use passive listeners to improve scrolling performance
    - Serve static assets with an efficient cache policy
    - Avoid an excessive DOM size
    - Minimize main-thread work  
- Accessibility
    - ARIA IDs are not unique
    - Links do not have a discernible name  
- Best practices
    - Uses deprecated APIs 
    - All front-end JavaScript libraries detected on the page
    - A strong Content Security Policy (CSP) significantly reduces the risk of cross-site scripting (XSS) attacks.  
- SEO
    - Links are not crawlable  

Javascripten borde uppdateras och optimeras. Kanske göra sig av med överflödiga bibliotek och tredjeparts javascript. Eftersom det är mycket bilder på sidan så skulle det förbättras av att man använde andra format.

[Krigshistoriepodden](https://www.krigshistoriepodden.com/){#krigshistoriepodden .linkheader}
----------------------- 

![krigshistoriepodden](image/krigshistoriepoddenv2.jpg?width=300&height=300&q=70){.krigshistoriepodden}

Kommentarer från google pagespeed:

- Opportunities (utvalda delar)
    - Reduce unused JavaScript
    - Reduce unused CSS  
- Diagnostics (utvalda delar)
    - Reduce the impact of third-party code
    - Minimize main-thread work
    - Reduce JavaScript execution time

En tydlig förbättring som kan göras är att vissa tredjepart widgets inte laddar normalt. Generellt att använda sig av mindre javascript bibliotek och tredjeparts tjänster.

</br>

Analys
-----------------------
</br>
<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ_JKK_w_zlTaDUbKYnGiqeNiihPPifgyEgMBNu4a9ghOBGHDqnKPxUOZMSIM64JVRnyQxlwsTmQj1r/pubhtml?widget=true&amp;headers=false" class="lightspeed-data-container"></iframe>
</br>

För dom flesta sidorna (Lynnandtonic excluderad) så verkar hantering av javascript i form av bibliotek och tredjepartstjänster vara den stora boven när det kommer till nätverkshastighet. Bildformat är också en vanlig anledning till förbättring enligt google pagespeed.

Lynnandtonic sticker ut lite med 100 i alla kategorier. 

Om man skulle rangorna dessa efter de fyra huvudkategorierna, performance, accessiblity, best practices och SEO så skulle det se ut så här (i ordningen bästa först).  
1. Lynnandtonic
2. Krigshistoriepodden
3. Jävligtgott  

Krigshistoriepodden och Jävliggott har lite samma problematik med javascript och widgets där den ena är marginelt bättre än den andra. Något som sticker ut är Lynnandtonic som verkar väloljad i alla avseenden. Alla är person sidor, men formatet är lite olika. Lynnandtonic är däremot utvecklad av någon som arbetar med design för just webben.

5 sekunder känns som den absoluta laddningtiden för alla element (och då är det bara lynnandtonic som klarar det testet). Däremot ser gärna jag att ansiktet utåt, eller headern laddar nästan direkt. Något som klaras av utan svårighet av Lynnandtonic, men tar lite längre tid för Jävliggott. Däremot tar det lite väl lång tid för krigshistoriepodden (trots bättre värden) och upplevs därför inte som lika mjuk i inladdnignen. 
Jag har bra uppkoppling och inga av sidorna är något större problem. Men man vill nog gärna tänka på att sidorna ska gå fort att i huvudsaklig del ladda in på sämre uppkoppling, ex 3G. 


Referenser
-----------------------

Beaird, J., & George, J. (2014). The principles of beautiful web design. SitePoint.

Övrigt
-----------------------

Den här analysen än skriven av Linus Söderberg