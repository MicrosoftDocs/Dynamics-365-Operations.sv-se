---
title: Projektkontrakt
description: "Denna artikel beskriver och ger exempel på de projektavtal som du kan skapa för olika typer av projekt och finansieringskällor, samt hur du kan hantera avtal och fakturaprojektkunder i Microsoft Dynamics 365 for Operations."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9f3bdbd147f3132d64e3b9ac2bdd37f7278ae18d
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="project-contracts"></a>Projektkontrakt

[!include[banner](../includes/banner.md)]


Denna artikel beskriver och ger exempel på de projektavtal som du kan skapa för olika typer av projekt och finansieringskällor, samt hur du kan hantera avtal och fakturaprojektkunder i Microsoft Dynamics 365 for Operations.

Typen av projektet som du skapar för ett projektavtal bestämmer vilken metod som används för att faktura projektkunderna. Du kan ändra ett projektavtal och det relaterade projektet, men du kan inte ändra projekttypen. 

Genom att använda ett projektkontrakt kan du fakturera ett eller flera projekt samtidigt. Projektkontraktet hjälper dig också att garantera att en enhetlig faktureringsprocedur används för varje delprojekt i en projektstruktur. 

Varje projekt som ska faktureras måste kopplas till ett projektkontrakt. Inställningar för ett projektkontrakt gäller för alla projekt och delprojekt som är kopplade till det projektkontraktet. 

Ett projektkontrakt kan ange en eller flera källor till finansieringen. Därför kan du dela faktureringen mellan flera finansiärer, ställa in finansieringsgränser så att inte finansieringskällor faktureras mer än ett angivet belopp och konfigurera finansieringsregler för debitering av omkostnader.

## <a name="funding-for-project-contracts"></a>Finansiering av projektkontrakt
Vissa projektkontrakt anger att flera parter delar ansvaret för att finansiera projektkostnaderna. Nedan följer några exempel:

-   En stort kund med flera avdelningar begär att finansiering för ett projekt delas per avdelning.
-   Ditt företag delar kostnaderna för ett stort projekt med en extern organisation.
-   Ett vägprojekt samfinansieras av två kommuner.
-   Ett broprojekt finansieras med statsbidrag och av ett privat företag.

I Microsoft Dynamics 365 for Operations kan du dela faktureringen för en enstaka transaktion eller ett helt projekt mellan flera kunder, anslag eller organisationer. 

I projekt med flera finansiärer kallas alla parter som bidrar till finansieringen av ett avancerat finansieringsprojekt för finansieringskällor. När kund, organisation eller ett anslag definieras som en finansieringskälla kan den tilldelas till en eller flera finansieringsregler. Finansieringsregler innehåller villkoren som bestämmer hur debiteringar fördelas till de olika finansieringskällorna för ett projekt. 

Eftersom artiklar i lager, till exempel sådana som anges på inköpsrekvisitioner och inköpsorder inte kan delas, kan kostnadsbeloppet inte delas mellan flera finansieringskällor vid distribution. Därför blir finansieringskällvärdet 0 (noll) tills lagerutleveransen bokförs. När lagerutleveransen bokförs fördelas kostnadsbeloppet enligt kontofördelningsreglerna för projektet.

Nedan följer några steg du kan ta för att göra det enklare att dela faktureringen mellan flera finansieringskällor:

-   Ange att alla transaktioner som anges för ett projekt använder samma försäljningsvaluta som projektkontraktet.
-   Ställ in finansieringsgränser, så att en finansieringskälla inte faktureras mer än ett angivet belopp mot ett projekt.
-   Konfigurera finansieringsregler och finansieringsgränser för varje anställd, artikel, kategori, kategorigrupp och transaktionstyp (eller för alla transaktionstyper).
-   Välj valfria start- och slutdatum för att definiera perioden då varje finansieringsregel är giltig.
-   Ange procentsatsen att varje finansieringskälla ansvarar för.
-   Ange vilken finansieringskälla som är ansvarig för avrundningsdifferenser som orsakas av finansieringsallokeringsberäkningar.
-   Ställ upp regler som avgör hur projektkostnader faktureras till externa kunder och debiteras interna organisationer.
-   Registrera transaktioner på ett spärrat finansieringskonto tills ytterligare finansieringen erhålls eller tills du väljer att ta kostnaderna internt.

Avgör vilken momsgrupp som associeras med en transaktion genom att söka igenom projektet efter en momsgrupptilldelning. Om ingen momsgrupptilldelning har gjorts på projektnivån genomsöks projektkontraktet.

### <a name="example-multiple-funding-sources-simple"></a>Exempel: Flera finansieringskällor (enkel)

I följande tabell finns scenarier för hantering av finansieringsallokering mellan flera finansieringskällor. Dessa scenarier baseras på följande antaganden:

-   Prioriteringsinställningar tas med i beräkningen av allokering av medel innan andra finansieringsregelvillkor tillämpas.
-   Inget datumintervall har angetts för att definiera perioden D när finansieringsregeln är giltig.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Scenario</strong></td>
<td><strong>Finansieringskälla </strong></td>
<td><strong>Allokeringsprocent </strong></td>
<td><strong>Allokeringsprioritet </strong></td>
</tr>
<tr class="even">
<td>Du vill fördela kostnader till en finansieringskälla tills dess medel har utnyttjats, fördela kostnader till en andra finansieringskälla tills dess medel har utnyttjats och slutligen fördela återstående kostnader till tredje finansieringskälla.</td>
<td><ul>
<li>Finansieringskälla 1</li>
<li>Finansieringskälla 2</li>
<li>Finansieringskälla 3</li>
</ul></td>
<td><ul>
<li>100 %</li>
<li>100 %</li>
<li>100 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
<li>3</li>
</ul></td>
</tr>
<tr class="odd">
<td>Du vill fördela 75 procent av kostnaderna till en finansieringskälla och 25 procent till en andra finansieringskälla. När någon av finansieringskällorna har utnyttjats betalar du återstående kostnader från en tredje finansieringskälla.</td>
<td><ul>
<li>Finansieringskälla 1</li>
<li>Finansieringskälla 2</li>
<li>Finansieringskälla 3</li>
</ul></td>
<td><ul>
<li>75 %</li>
<li>25 %</li>
<li>100 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
<tr class="even">
<td>Du vill fördela 75 procent av kostnaderna till en finansieringskälla och 25 procent till en andra finansieringskälla. När någon av finansieringskällorna har utnyttjats delar du återstående kostnader mellan en tredje och en fjärde finansieringskälla.</td>
<td><ul>
<li>Finansieringskälla 1</li>
<li>Finansieringskälla 2</li>
<li>Finansieringskälla 3</li>
<li>Finansieringskälla 4</li>
</ul></td>
<td><ul>
<li>75 %</li>
<li>25 %</li>
<li>50 %</li>
<li>50 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
<li>2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Du vill fördela de första 25 procenten av kostnaderna till en finansieringskälla och resten till en andra finansieringskälla.</td>
<td><ul>
<li>Finansieringskälla 1</li>
<li>Finansieringskälla 2</li>
</ul></td>
<td><ul>
<li>25 %</li>
<li>100 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a>Exempel: Flera finansieringskällor (komplex)

Du har tre finansieringskällor som du vill använda i följande ordning:

1.  Använd finansieringskälla 2 och 3 lika tills finansieringskälla 2 har utnyttjats.
2.  Fortsätt att använda finansieringskälla 3 tills har utnyttjats.
3.  Använd finansieringskälla 1 när finansieringskälla 3 har utnyttjats.

Om du vill uppnå målet måste du göra följande:

-   Ställ in finansieringsgränser för finansieringskälla 2 och 3 med deras respektive belopp.
-   Skapa följande finansieringsregler:
    -   Regel 1 (prioritet 1): Fördela 50 procent av transaktionerna till finansieringskälla 2 och 50 procent till finansieringskälla 3.
    -   Regel 2 (prioritet 2): Fördela 100 procent av transaktionerna till finansieringskälla 3.
    -   Regel 3 (prioritet 3): Fördela 100 procent av transaktionerna till finansieringskälla 1.

Det här fungerar eftersom transaktioner kontrolleras mot regler och gränser som fastställer om några av dem gäller för transaktionen. Om inga specifika regler eller gränser gäller för transaktionen gäller regeln Alla transaktioner. Regeln Alla transaktioner matchar alla transaktioner. 

Om en regel som matchar en transaktion används procentandelen som har allokerats i regeln först, men endast efter att matchningarna kontrolleras mot gränserna som har ställts in. Om en gräns har uppfyllts och en finansieringskällas medel har utnyttjats, ignoreras finansieringsregeln som är kopplad till finansieringsgränsen och programmet söker efter nästa regel som gäller. 

I vissa fall kan bara en del av en transaktion fördelas under en regel. Detta kan inträffa eftersom en gräns uppnås när transaktionen fördelas. I det här fallet allokeras bara ett visst belopp enligt den regeln, till exempel 50 procent till varje finansieringskälla. Detta är fallet i regel 1 som beskrevs tidigare i det här avsnittet. Resten fördelas enligt nästa regel i sekvensen. 

Följande tabell undersöker det här scenariot noggrannare.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Fokus </strong></td>
<td><strong>Detaljer</strong></td>
</tr>
<tr class="even">
<td>Finansieringsregler</td>
<td><ul>
<li>Regel 1 (prioritet 1): Alla transaktioner. Fördela finansieringskälla 2 till 50 % och finansieringskälla 3 till 50 %.</li>
<li>Regel 2 (prioritet 2): Alla transaktioner. Fördela finansieringskälla 3 till 100 %.</li>
<li>Regel 3 (prioritet 2): Alla transaktioner. Fördela finansieringskälla 1 till 100 %.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Finansieringsgränser</td>
<td><ul>
<li>Gräns för finansieringskälla 1 = 10 000,00</li>
<li>Gräns för finansieringskälla 2 = 500,00</li>
<li>Gräns för finansieringskälla 3 = 750,00</li>
</ul></td>
</tr>
<tr class="even">
<td>Transaktion 1</td>
<td><strong>Transaktionsbelopp:</strong> 100,00,<strong>Finansiering:</strong> Transaktionen betalas endast enligt regel 1, eftersom transaktionen är fullständigt betalad efter att regel 1 tillämpas. Transaktionen finansieras lika mellan finansieringskälla 2 och 3.
<ul>
<li>Finansieringskälla 2: 50,00</li>
<li>Finansieringskälla 3: 50,00</li>
</ul></td>
</tr>
<tr class="odd">
<td>Transaktion 2</td>
<td><strong>Transaktionsbelopp:</strong> 5 000,00<strong>Finansiering:</strong> Transaktionen finansieras enligt alla tre reglerna.<strong>Regel 1</strong>
<ul>
<li>Finansieringskälla 2: 450,00</li>
<li>Finansieringskälla 3: 450,00</li>
</ul>
<strong>Regel 2</strong>
<ul>
<li>Finansieringskälla 3: 250,00 (= 750,00 - 50,00 - 450,00)</li>
</ul>
<strong>Regel 3</strong>
<ul>
<li>Finansieringskälla 1: 3 850,00 (= 5 000,00 - 450,00 - 450,00 - 250,00)</li>
</ul></td>
</tr>
<tr class="even">
<td>Total finansiering som distribueras för varje finansieringskälla</td>
<td><ul>
<li>Finansieringskälla 1: 3 850,00</li>
<li>Finansieringskälla 2: 500,00</li>
<li>Finansieringskälla 3: 750,00</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a>Faktureringsregler
När du förhandling om ett projektkontrakt med en kund, kan du definiera hur och när du kan fakturera kunden för arbete på ett projekt. När du har ställt in projektkontraktet och projektet kan du ställa in faktureringsregler för projektet. Faktureringsreglerna baseras på projektvillkoren som anges i projektkontraktet. Vilka faktureringsregler som du kan skapa beror på villkoren i projektkontraktet och typen av projekt, till exempel Tid och material eller Fastpris, som du associerar med faktureringsregeln. Du kan skapa mer än en faktureringsregel för ett projektkontrakt. Du kan också tilldela en faktureringsregel till projekt, som associeras med samma projektkontrakt, och du har liknande faktureringstermer. 

Du kan ställa in följande faktureringsregler:

-   **Leveransenhet** – Fakturera en kund när du slutför en leveransenhet. Du definierar enheter för leverans i kontraktet.
-   **Förlopp** – Fakturera en kund när du slutför en viss procentadel av projektet. Du kan ställa in en faktureringsregel automatiskt att beräkna den uppsagda procent av arbete, eller så kan du manuellt vill beräkna hur många procent av arbete som är avslutat och beloppet för att fakturera kunden.
-   **Milstolpe** – Fakturera en kund för hela beloppet för en projektmilstolpe när den uppnås.
-   **Avgift** – Fakturera en kund för dina tjänster plus en hanteringsavgift, vanligtvis en procentandel av kostnaden för tjänsterna.
-   **Tid och material** – Fakturera en kund värdet av tid och material som användes i ett projekt.

För alla typer av faktureringsregler kan du ange en kvarhållandeprocentsats som dras av från kundfakturor tills ett projekt når en avtalad fas. Betalningskvarhållandeprocentsatsen anges i projektkontraktet. Beloppet beräknas på och dras av från det totala värdet av raderna i en kundfaktura. 

För faktureringsreglerna **Tid och material** och **Förlopp** kan du tilldela debiterbara kategorier. Debiterbara kategorier visar vilka transaktioner som ska inkluderas i kundfakturor. 

När du är redo att fakturera kunden är beloppet på fakturan för projektet beräknat baserat på faktureringsreglerna och ett projektfakturaförslag genereras. 

Följande avsnitt innehåller exempel som visar hur du ställer in och hanterar faktureringsregler för ett projekt.

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a>Exempel: Skapa en faktureringsregel som baseras på antalet levererade enheter

Din organisation avtalar att tillhandahålla totalt fem utbildningssessioner till en kunds medarbetare till en kostnad på 10 000 per utbildningssession. Du fakturerar kunden efter varje utbildningssession. 

När du ställer in faktureringsreglerna för kontraktet använder du följande värden:

-   Enheten för leverans är en träningsession.
-   Enhetspriset är 10,000 per träningsession.
-   Totalt antal enheter är fem träningssessioner.

När du har slutfört en utbildningssession kan du skapa en faktura på 10 000 för den första enheten som levererades och skicka fakturan till kunden.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a>Exempel: Skapa en faktureringsregel som baseras på en viss procent av projektslutförande (manuell beräkning)

Din organisation, ett datakonsultföretag, ingår ett avtal med en kund om att utveckla en del av en produkt som kunden utvecklar. Organisationen förbinder sig att leverera programvarukoden över en period på sex månader. Kunden förbinder sig att betala din organisation totalt 100 000 för arbetet. Du skapar en faktureringsregel för att fakturera kunden baserat på en procentsats färdigt arbete i projektet enligt avtalet.

-   I slutet av den första månaden träffar du kunden för att bestämma hur många procent av arbetet som har slutförts. Vid granskning av projektet beslutar du och kunden att projektet är slutfört till 15 procent.
-   Du skapar en faktura på 15 000 (15 procent av 100 000) och skickar den till kunden.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a>Exempel: Skapa en faktureringsregel som baseras på en viss procentandel av projektslutförande (automatisk beräkning)

Din organisation, en programutvecklingsfirma, går med på att sammanställa ett lönelisteredovisningspaket till en kund för 30 000. Kunden förbinder sig att betala din organisation baserat på procentandelen slutfört arbete. Du beräknar att projektkostnaderna är 20 000. Projektkontraktet anger arbetskategorierna som används i faktureringsprocessen. Du ställer in faktureringsregler som automatiskt beräknar fakturabelopp för procent av arbete, som utförs för varje kategori. Du ställer in en budget för varje kategori:

-   **Utveckling** – kostnad på 15 000 och intäkter på 20 000
-   **Installation** – kostnad på 5 000 och intäkter på 10 000

När du skapar en kundfaktura för första gången, är fakturabeloppet automatiskt beräknat baserat på följande information:

-   Efter en månad skickar arbetaren en tidrapport för projektet. Kostnaden för arbetarens timmar är 5 000 för utveckling och 1 000 för installation. Utvecklingsarbetet är 33 procent klart (faktisk kostnad 5 000/budgeterad kostnad 15 000) och installationsarbetet är 20 procent klart (faktisk kostnad 1 000/budgeterad kostnad 5 000).
-   Fakturabeloppet på 8 667 beräknas automatiskt (33 procent av 20 000 + 20 procent av 10 000).
-   Du skapar en faktura på 8 667 och skickar den till kunden.

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a>Exempel: Skapa en faktureringsregel som baseras på överenskomna milstolpar

Din organisation, en management-konsultfirma, genomför marknadsundersökningar för en konsumentprodukt som kunden planerar att sälja. Kunden förbinder sig att använda dina tjänster för en period på tre månader som startar i mars, och förbinder sig att betala din organisation 50 000. Projektet har tre milstolpar:

-   Milstolpe 1: Samla in konsumentdata – 31 mars
-   Milstolpe 2: Analysera konsumentdata – 30 april
-   Milstolpe 3: Framlägga ett produktgenomförbarhetsförslag – 31 mars

Kunden förbinder sig att betala din organisation 10 000 för den första milstolpen och 20 000 för den andra och 20 000 för den tredje milstolpen. 

När du ställer in projektkontrakt går du med på att fakturera kunden baserat på den slutförda milstolpen. Inställningen av faktureringsregler inkluderar följande steg:

-   Definiera projektmilstolparna.
-   Definiera beloppet att fakturera kunden vid slutförande av varje milstolpe.

När den första milstolpen är klar de 31 mars, markerar du milstolpen som slutförd och skapar sedan en faktura med beloppet 10 000 som skickas till kunden. Du kan inte skapa en faktura för en milstolpe förrän du har markerat milstolpen som slutförd.

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a>Exempel: Skapa en faktureringsregel baserad på tjänster plus en förvaltningsavgift

Din organisation, en management-konsultfirma, går med på att utföra marknadsundersökningar för att utvärdera genomförbarheten av en produkt som kunden, ett butiksföretag, utvecklar. Avtalets villkor anger att du tillhandahåller tjänster från de tre bästa managementkonsulterna som genomför undersökningen baserat på tid och material. Kunden går med på att betala 100 per timme plus en ytterligare administrationsavgift på 10 procent för konsulttimmar som debiteras projektet. 

När du ställer in projektkontraktet skapar du en faktureringsregel som lägger till en 10 procents administrationsavgift för konsulttimmar som debiteras projektet. 

När du skapar en faktura för kunden, kommer kunden att faktureras en 10 procent administrationsavgift plus kostnaden för konsulttimmarna. Om till exempel de tre konsulterna arbetade totalt 200 timmar på projektet skapas en faktura med beloppet 22 000 med följande beräkning:

-   200 timmar, 100 per timme = 20 000
-   10 procent hanteringsavgift = 2 000
-   Totalt fakturabelopp = 22 000

Om avgifter är momspliktiga för en kund och du väljer en momsgrupp i projektkontraktet, anges momsgruppen automatiskt i en faktureringsregel för avgifter.

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a>Exempel: Skapa en faktureringsregel för tids- och materialvärde

Din organisation, ett datakonsultföretag, avtalar att tillhandahålla fem tekniska konsulter att arbeta på ett programvaruutvecklingsprojekt för en kund under nästa halvår. Kunden förbinder sig att betala 150 för varje konsulttimme plus kostnaden för kontorsmaterial. Din organisation skickar en faktura till kunden i slutet av varje månad. 

När du ställer in projektkontraktet går du med på att fakturera kunden varje månad för tid och material i projektet. Du skapar en faktureringsregel som omfattar följande information:

-   Kontraktsperioden är sex månader.
-   Konsulttiden beräknas till ett värde av 150 per timme.
-   Kontorsvaror faktureras till självkostnad och totalkostnaden för projektet får inte överstiga 10 000.
-   Du skapar en kundfaktura i slutet av varje månad under projektet.

Under den första månaden registrerades totalt 800 timmar av konsulterna i projektet. Kostnaden för kontorsmaterial som debiteras projektet är 2 000. I slutet av månaden skapar du en faktura på 122 000 (800 timmar för 150 per timme plus 2 000 för kontorsmaterial).




