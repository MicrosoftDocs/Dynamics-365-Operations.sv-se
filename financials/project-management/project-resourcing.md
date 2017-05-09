---
title: "Resurshantering för projekt"
description: "Det här avsnittet innehåller information om resurshantering för projekt."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: cmercado
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: c29c95fc6abd13e668c44d3ccf437bb0e879e46b
ms.lasthandoff: 03/31/2017


---

# <a name="project-resourcing"></a>Resurshantering för projekt

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om resurshantering för projekt.

En utmaning för projektledare och resurschefer under projektplanläggningsfasen är resursallokeringen, där de måste bestämma och reservera rätt resurser för arbetet i ett projekt. I Microsoft Dynamics 365 for Operations resurshanteringsfunktioner för projekt kan du definiera roller som behandlas som tillfälliga resurser, som kan reserveras för ett visst engagemang eller delar av ett engagemang. Den här typen av resurshantering låter projektledare och resurschefer slutföra följande uppgifter:

-   Definiera en roll som har begärt kompetenserna som gör det enklare att matcha resurser.
-   Använd roller för att definiera en ursprunglig engagemangstidsplan som baseras på reserverade resurser.
-   Beräkna kostnader och konfigurera en ursprunglig budget baserad på tilldelade roller och resurser för ett projekt.
-   Använd roller för att beräkna antalet resursreserveringar som krävs för respektive engagemang.
-   Beräkna antalet resurser som krävs för hela livscykeln för ett projekt.
-   Gör ett utkast till en uppdelad arbetsstruktur med hjälp av de ursprungliga resurstilldelningarna.

[![Projektets livscykel](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg) 

I takt med att projektplanläggningen fortsätter, kan planerade resurser ersättas med bemannade resurser. Projektledaren kan också gå tillbaka och uppdatera resursreservationerna under alla projektfaserna.

## <a name="set-up-project-resources"></a>Ställ in projektresurser
Du måste ställa in en kalender och associera den till en medarbetare eller en arbetare. Kalendern används för att kunna tidsplanera projektet och arbetstiden för de resurser som har reserverats för projektet. Under kalenderinställningarna, projektledare kan utföra resursutjämning som en del av resursoptimering. Baserat på kalendertidsplanen kan begränsningar placeras på resurser. Du kan ställa in en kalender på sidan **Kalendrar**. 

När du ställer in en arbetare som en projektresurs du kan välja bland arbetare som arbetar i företaget som du ställer in resurser för, eller välja arbetare från andra företag inom din organisation. Dessa är koncerninterna resurser. Följande procedurer förklarar hur du ställer in en arbetare som projektresurs inom ditt företag och hur du ställer in en koncernintern projektresurs.

### <a name="set-up-a-worker-as-a-project-resource"></a>Ställ in en arbetare som en projektresurs

1.  På sidan **Arbetare**, i listan **Arbetare**, välj den arbetare som du lägger till som en projektresurs och öppna arbetarens post.
2.  I åtgärdsfönstret klickar du på **Projekt** &gt; **Inställningar** &gt; **Projektinställning**.
3.  Välj en kalender och stäng sedan sidan.

Du kan även ange standardprojekt för en resurs som en typ av förtilldelning. Förtilldelningar kan användas när resurschefen eller projektledaren vet vilka projekt att resursen ska arbeta med i förväg. Förtilldelningar kan också baseras på en begäran av en projektsponsor eller kund. Du förtilldelar ett projekt genom att välja lämpligt projekt på sidan **Tilldela projekt**, på **Projekt** fliken, i listan **Resterande projekt**.

### <a name="set-up-an-intercompany-resource"></a>Ställa in en koncernintern resurs

När du ställer in en arbetare som en koncernintern resurs måste du slutföra inställningarna i det långivande företaget och det lånande företaget. 

**I det långivande företaget:**

1.  I Dynamics 365 for Operations, kontrollera att det långivande företaget har valts och slutför sedan proceduren ovan, "Ställ in en arbetare som en projektresurs".
2.  Gå till **Redovisning **&gt; **Inställningar för bokföring **&gt; **Koncernintern redovisning**. Klicka på **Ny**.
3.  I fältet **ID för juridisk person **, välj det långivande företaget. Fyll i återstående fält efter behov och klicka sedan på **Spara**.
4.  Gå till **Projekthantering och redovisning **&gt; **Inställningar **&gt; **Priser ** &gt; **Internpris**.** **
5.  I formuläret **Internpris **, klicka på **Nytt** och i fältet **Lånande juridisk person **, välj lämpligt företag.
6.  Om du bara vill låna ut den resurs som du skapade i början av detta avsnitt till det lånande företaget, väljer du namnet på resursen som du har skapat i fältet **Resurs**. Om du vill att alla resurser inom företaget ska vara tillgängliga för det lånande företaget lämnar du fältet **Resurs ** tomt.
7.  Gå till **Projekthantering och redovisning **&gt; **Inställningar **&gt; **Parametrar för projekthantering och redovisning**, och på fliken **Koncerninternt ** ställer du in fältet **Aktivera koncernintern resursplanering och tidrapporter ** till **Ja**.

**I det lånande företaget:**

1.  Gå till **Projekthantering och redovisning** &gt; **Projektresurser** &gt; **Resurslista**.
2.  I sökfiltret anger du namnet på resursen som du skapade i föregående procedur för det långivande företaget, för att kontrollera att namnet finns i resurslistan för det lånande företaget.

## <a name="manage-resource-competencies"></a>Hantera resurskompetenser
Resurskompetenser är en viktig del av resurshantering. Kompetenser kan användas som en jämföra för att bestämma resurser som har rätt balans av utbildning, färdigheter, certifiering och projekterfarenhet. Du bör ställa in informationen för varje resurs och uppdatera den regelbundet. På så sätt kan du maximera förmågor när specifika resurskompetenser matchas under projektresurstilldelning. [![Exempel på färdigheter, certifieringar, utbildning och projekterfarenhet](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg) 

Följande procedurer innehåller information om hur du ställer in vissa kompetenser för en resurs. 

Om du vill ställa in kompetenser för en arbetare kan du använda antingen **Arbetare** listsidan i Personal eller **Resurser** listsidan i Projekthantering och redovisning. För följande procedurer används listsidan **Arbetare** i Personal.

### <a name="set-up-competencies-certificates"></a>Ställa in kompetenser: Certifikat

1.  På listsidan **Arbetare**, välj raden för arbetaren som du lägger till certifikatinformation för.
2.  I Åtgärdsfönster, på fliken **Arbetare**, i gruppen **Kompetenser** klickar du på **Certifikat**.
3.  Klicka på **Ny**.
4.  I fältet **Certifikattyp**, välj **PMP**.
5.  I fältet **Startdatum**, välj **10/1/2015**.
6.  Klicka på **Spara** och stäng sedan sidan.

### <a name="set-up-competencies-skills"></a>Ställ in kompetenser: Kompetenser

1.  Kontrollera på listsidan **Arbetare** att arbetaren som du använde i den föregående proceduren markeras fortfarande. Sedan i Åtgärdsfönster, på fliken **Arbetare**, i gruppen **Kompetenser** klickar du på **Kompetenser**.
2.  Klicka på **Ny**.
3.  I fältet **Kompetens**, välj **Projekthantering**.
4.  I fältet **Nivå**, välj **5 Expert**.
5.  I fältet **Nivådatum**, välj **1-/14/2014**.
6.  Ange i **Erfarenhetsår** fältet, **10**.
7.  Klicka på **Spara** och stäng sedan sidan.

## <a name="create-a-new-project"></a>Skapa ett nytt projekt
1.  Klicka på **Projekthantering och redovisning** &gt; **Arbetsytor** &gt; **Projekthantering**.
2.  Klicka på **Nytt projekt** och ange sedan följande värden:
    -   **Projekttyp** – tid och material
    -   **Projektnamn** – XYZ uppgraderingsfas 2
    -   **Projektgrupp** – TM\_WIP
    -   **Projektkontrakt-ID:** – 00000002
3.  Klicka på **Skapa projekt**.

### <a name="assign-a-resource-to-a-project"></a>Tilldela en resurs till ett projekt

1.  Klicka på **Personal** &gt; **Arbetare** &gt; **Arbetare**.
2.  I listan **Arbetare**, markera posten för den arbetare som kompetenser ställts in för tidigare och öppna arbetarposten.
3.  I Åtgärdsfönstret, på fliken **Projekt**, i gruppen **Inställningar**, klicka på **Tilldela projekt**.
4.  På sidan **Resursvalidering för projekttilldelningar**, klicka på fliken **Projekt**.
5.  I **Lägg till projektet i valda projekt**, filtrera på projektet, XYZ uppgraderingsfas 2
6.  I fönstret **Resterande projekt**, välj ett projekt och klicka sedan på pilen för att lägga till det i fönstret **Valda projekt**.
7.  Stäng sidan.

Om det behövs kan du också tilldela kategorier för en resurs. Kategoritypen är antingen Kostnad eller Intäkt. Detta avgörs av din organisation. Om det inte finns några tilldelade kategorier för resursen, slår Dynamics 365 for Operations upp standardkategorin på timpriser för kostnader och intäkter.

### <a name="set-up-project-resource-and-role-characteristics"></a>Ställ in projektresurs och rollegenskaper

En projektledare kan använda projektresurshanteringsfunktionen för att skapa roller som krävs för projektet. Roller kan användas när bekräftade resurser fortfarande är okända när resurser reserveras. Roller kan tillfälligt reserveras som planerade resurser, så att du kan fortsätta projektplanläggningsfaserna. 

[![Exempel på en roll](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scenario:** Contoso anlitades för att slutföra ett tids- och materialprojekt som har ett godkänt projektramverk. Juniorprojektledaren avslutar fortfarande omfånget för projektet. Den resursansvarige identifierar för närvarande specifika resurser som ska reserveras för arbete på det nya projektet. En av rollerna som begärdes av projektsponsorn, på grund av projektets viktiga art, är seniorprojektledaren. Den resursansvarig måste skaffa den nya resursen och definiera rollen i systemet, om juniorprojektledaren kräver resursinformationen under projektplaneringen. 

Följande steg visar hur resursansvarig kan ställa in rollen Seniorprojektledare och associera resursegenskaper med den. Senare rollen kan användas för att söka efter tillgängliga resurser som matchar de nödvändiga resurskompetenserna.

1.  Klicka på **Projekthantering och redovisning** &gt; **Inställningar** &gt; **Resurser** &gt; **Ställ in roller**.
2.  Klicka på **Nytt** och ange sedan följande värden:
    -   **Roll-ID** – Senior projektledare
    -   **Beskrivning** – Senior projektledare
3.  Klicka på **Skapa**.
4.  Välj **Senior projektledare**-rollen och klicka sedan på **Konfigurera egenskaper**.
5.  I fältet **Egenskapstyp**, välj **Kompetens**.
6.  I fältet **Tillgängliga egenskaper**, ange den färdighet som du söker efter.
7.  I fältet **Egenskapstyp**, välj **Certifikat**.
8.  I fältet **Tillgängliga egenskaper**, ange den certifikattyp som du söker efter.
9.  Klicka på **OK** och stäng sidan.

### <a name="assign-a-project-resource-to-a-project"></a>Tilldela en projektresurs till ett projekt

1.  Klicka på **Projekthantering och redovisning** &gt; **Allmänt** &gt; **Projekt** &gt; **Alla projekt** och öppna projektet **XYZ uppgraderingsfas 2**.
2.  På fliken **Projektteam och tidsplanering**, klicka på **Lägg till**.
3.  I fältet **Roll**, välj **Teammedlem**.
4.  Klicka på **Boka från kalender**.
5.  På **Resurstillgänglighet**-sidan, klicka på **Visa inställningar**.
6.  På sidan **Justera visningsinställningar**, ange följande värden:
    -   **Vy för format för datumintervall** – Dag
    -   **Visa beskrivningar av tillgänglighet** – Ja
    -   **Visa resterande kapacitet** – Ja
7.  Välj en resurs i listan över resurser.
8.  Klicka på **Fast bokning** &gt; **Total kapacitet**.
9.  Stäng sidan.

### <a name="assign-a-resource-to-a-default-role"></a>Tilldela en resurs till en standardroll

Om du vill hjälpa projektledare eller resursansvariga kan du gå nedåt i resurserna som kan reserveras för ett projekt. Du kan associera en standardroll med en befintlig resurs eller en nyligen anskaffad resurs. Exempelvis när Daniel anställdes hade han erfarenhet och sakkunskap som passade för rollen Affärsanalytiker. Resursansvarige tilldelade den här rollen som Daniels standardroll. Därefter lade resursansvarige till Daniel i en pool med affärsanalytiker som är tillgängliga för arbete i projekt. 

Under resursreserveringen kan projektledare filtrera rollresurserna som är tillgängliga för arbete i projekt. De kan använda den här informationen som ett villkor när de använder beslutsanalys för flera kriterier under resursuppfyllelse. De kan också lägga till andra resursegenskaper till filtret om du vill söka efter resurser som har specifika färdigheter, utbildning och erfarenheter för ett visst projekt. 

**Scenario:** Ett godkänt projekt har startat och den seniora projektledarrollen reserverades som en planerad resurs under projektplanläggningsfasen. Resurschefen har nu fått en resurs för att uppfylla den seniora rollen som projektledare.

1.  Klicka på **Projekthantering och redovisning** &gt; **Projektresurser** &gt; **Resurslista**.
2.  I listan **Resurs**, välj **Daniel Goldschmidt**.
3.  Klicka på **Projektresurs** &gt; **Underhåll** &gt; **Resursroll**.
4.  Klicka på **Nytt** och ange sedan följande värden:
    -   **Giltighet** – (det aktuella datumet)
    -   **Utgång** – Aldrig
    -   **Roll** – Senior projektledare
5.  Klicka på **Spara** och stäng sedan sidan.
6.  På fliken **Kompetenser**, lägg till färdigheten **ProjectMgmt** och **PMP**.

## <a name="set-up-role-based-pricing"></a>Ställ in rollbaserad prissättning
Alla kostnader, försäljningar och internpriser kan ställas in för roller.

1.  Klicka på **Projekthantering och redovisning** &gt; **Inställningar** &gt; **Priser** &gt; **Försäljningspris (timme)**.
2.  Klicka på **Ny**.
3.  Ange ett ikraftträdandedatum.
4.  Välj en roll i kolumnen **Roll**.
5.  I kolumnen **Priser**, ange ett pris för den valda resursrollen.

## <a name="form-a-project-team"></a>Skapa ett projektteam
Om du vill använda de roller som redan har ställts in i ett projekt, måste en projektledare associera rollerna med projektet. Flera roller kan tilldelas för ett projekt och Dynamics 365 for Operations ger automatiskt dessa roller etiketter under reserveringen för att förhindra förvirring. Om till exempel projektledaren kräver tre programingenjörer, genereras automatiskt tre roller för programingenjör som har etiketterna programingenjör 1, programingenjör 2 och programingenjör 3. Om rollen tidigare fått egenskaper, används de som ett filter för sökningar efter en resurs. Ytterligare egenskaper kan läggas till som krävs för att begränsa sökningen. 

Visningsinställningar kan också anpassas för att ge en bättre vy av resurstillgänglighet. Det finns alternativ för att visa tim, dag, vecka, månad, kvartalsvis och årlig tillgänglighet. Det finns även alternativ för att visa återstående och tillgänglig kapacitet för resurser. Det här alternativet är användbart för tidsadministration, när du vill beräkna tillgänglig tid för aktiviteter eller resurstillgänglighet. 

Projektledaren kan välja en roll på sidan och sedan, om det finns en tillgänglig resurs som passar behovet, välja att reservera en resurs för att fylla rollen. Observera att resurserna inte måste reserveras vid denna tidpunkt under planeringsfasen. När du skapar en struktur kan du ersätta roller med bemannade resurser för projektet. Om roller ersättas med bemannade resurser i strukturen uppdaterar inställningen av resursen automatiskt projektteamslistan och tidsplaneringen. 

[![Projektteam som innehåller både roller och faktiska resurser](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Projektchefen har olika alternativ för att boka resurser för ett projekt, till exempel **Remaining capacity**, **Full capacity**, **Capacity percentage** och **Specify hours**. Dessa bokningsalternativ kan annulleras när som helst om resurstilldelningen ändras. Två typer av bokningar stöds:

-   **Fast bokning** – Resursreservationen godkändes och bekräftades för att arbeta på engagemanget under den angivna varaktigheten.
-   **Preliminär bokning** – Resursreservationerna godkändes preliminärt för att arbeta på engagemanget för den angivna varaktigheten.

Följande procedur förklarar hur du skapar ett projektteam.

### <a name="create-a-project-team"></a>Skapa ett projektteam

1.  På listsidan **Alla projekt**, välj ett projekt och klicka sedan på **Redigera**.
2.  På fliken **Projektteam och tidsplanering**, i fältet **Schemalagt slutdatum**, ange schemastartdatumet plus en månad. Om till exempel schemastartdatumet är 24 juni 2017 (24/06/2017), ange **24/07/2017**.
3.  Klicka på **Lägg till**.
4.  I **Lägg till roller i projektet**-fönstret, i **Roll **-fältet, välj **Senior projektledare**.
5.  Klicka på **Kompetenser som krävs**.
6.  På **Välj egenskaper**-sidan markeras de egenskaper som du tidigare angett för rollen senior projektledare som standard. Klicka på **OK**.
7.  På **Lägg till roller i projektet**-sidan i **Antal resurser**-fältet, ange **1**.
8.  I **Resurs**-fältet visar sökningen alla resurser som har begärt kompetenserna. Välj **Daniel Goldschmidt** och klicka sedan på **Skapa**.
9.  På **Projekt**-sidan, klicka på **Lägg till**.
10. I **Lägg till roller i projektet**-fönstret, i **Roll**-fältet, välj **Teammedlem**. I fältet **Antal resurser**, ange **5**.
11. Klicka på **Skapa**.
12. På sidan **Projekt**, klicka på **Uppfyll resurs**.

## <a name="resource-capacity-synchronization"></a>Synkronisering av resurskapacitet
Följande processer för synkronisering av resurser hjälper till att garantera att information om kalendern och om baskalendern sipprar ned i tidsplanering av projektresurser. Om kalendern ändras gör processerna de nödvändiga uppdateringarna av planeringen av projektresurser. Processerna kan också hjälpa till att förbättra prestandan, eftersom kalenderns resursinformation synkroniseras i förväg, så att uppdateringar av resurstidsplaneringsinformation sker snabbare. Vi rekommenderar att du planerar processer som en batch i stället för en i taget. Annars finns det en risk att någon glömmer inklusive datum när informationen synkroniserades senast. Om inklusive datum inte används, luckor kan inträffa under datumsynkronisering.

### <a name="calendar-synchronizationmediaprojectresourcing04-1024x471jpg"></a>![Kalendersynkronisering](./media/projectresourcing04-1024x471.jpg)

**Synkronisera kapacitetsuppföljningar för resurs**

Synkroniseringsprocessen har utformats för att synkronisera all information om resurskalendrarna. Informationen omfattar baskalenderinformation om alla ändringar i kapacitetsregistret för projektets resurskalender. Om nya resurser läggs till i projektet, synkroniseringen hjälper till att säkerställa att den uppdaterade kalenderinformationen är tillgänglig. Den här synkroniseringen kan göras när som helst. 

Vi rekommenderar att du använder en batch. Alternativen är tillgängliga för att synkronisera kapacitetsreservationer.

-   Klicka på **Projekthantering och redovisning** &gt; **Periodisk** &gt; **Kapacitetssynkronisering** &gt; **Synkronisera kapacitetsuppföljningar för resurs**.

| Alternativ | beskrivning                                                                                                                                                                                          |
|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ja    | Synkronisera alla resursdata med information om kalender och om baskalender och ersätt all information i projektets kalender för resurskapacitet.                                                  |
| Nej     | Synkronisera resursdata som baseras på en datumintervallkod och de angivna start- och slutdatumen. Det här alternativet tar inte bort befintliga data och uppdaterar information endast för nyligen tillagda resurser. |

[![Synkroniseringsprocess](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Konfigurera roller för strukturmallar
Projektledare kan ställa in strukturmallar de kan använda när de skapar en struktur för nya projekt. Projektledare kan lägga till roller när de skapar en mall. Använd följande procedur för att tilldela en roll till en strukturmall.** **

1.  Klicka på **Projekthantering och redovisning** &gt; **Inställningar** &gt; **Projekt** &gt; **Uppdelade arbetsstrukturmallar**.
2.  Klicka på **Information** för en vald strukturmall.
3.  Välj en uppgift i listan och sedan, i **Roll**-fältet, välj en roll som ska tilldelas uppgiften.

### <a name="work-with-a-wbs"></a>Arbeta med en struktur

Du kan skapa en ny struktur, eller så kan du kopiera en struktur från en befintlig strukturmall. En projektledare kan enkelt hantera resurserna genom att tilldela roller till nya uppgifter på strukturen. Roller kan ersättas när en resurs har anskaffats eller efter en bekräftad resurs som ska arbeta med uppgiften identifierats. Denna flexibilitet låter projektledare utföra följande uppgifter:

-   Identifiera det antal resurser som krävs för strukturarbetspaket.
-   Uppskatta projektkostnader.
-   Fastställa en preliminär budget.
-   Beräkna aktivitetvaraktighet baserat på roller och resurser.
-   Utveckla alla projektledningsplaner baserat på den tillgängliga projektinformationen.

Ytterligare alternativ har lagts till i strukturen för en bättre användning av resursplaneringsfunktionerna.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Alternativ</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Resurstilldelningar</td>
<td>Visa tilldelade resurser, datum, antalet timmar och bokningstyp för uppgifter på strukturen.</td>
</tr>
<tr class="even">
<td>Autogenerera team</td>
<td>Automatiskt lägg till planerade resurser genom att använda roller som associeras med en uppgift. Dynamics 365 for Operations föreslår automatiskt planerade resurser genom att använda beslutsanalys för flera kriterier baserat på roller. När rollerna och insatsen (timmar) har angetts för uppgifterna i en struktur, och strukturen har frisläppts, klicka på <strong>Autogenerera team</strong>. Det begärda antalet planerade resurser läggs till i strukturen och på fliken <strong>Projekt och tidsplanering av team</strong>.</td>
</tr>
<tr class="odd">
<td>Resurs (listruta)</td>
<td>På sidan <strong>Starta resurstilldelning</strong> kan du välja resurser att preliminär- eller fastboka utifrån den angivna varaktigheten. Du kan justera vyinställningarna om du vill visa och ange längden för resursaktiviteter. Du kan välja och tilldela resurser på nivån för arbetspaketet genom att använda följande alternativ:
<ul>
<li><strong>Godkänn</strong> – Bekräfta ändringarna för resursen som har tilldelats en uppgift.</li>
<li><strong>Avbryt</strong> – Avbryt ändringarna för resursen som har tilldelats en uppgift.</li>
<li><strong>Tilldela automatiskt</strong> – Det här alternativet väljer en tillgänglig bemannad resurs med en matchande roll för den valda uppgiften.</li>
</ul></td>
</tr>
</tbody>
</table>

1.  Klicka på **Projekthantering och redovisning** &gt; **Projekt** &gt; **Alla projekt**.
2.  I listan, välj projektet **XYZ uppgraderingsfas 2**.
3.  Klicka på **Plan** &gt; **Aktiviteter** &gt; **Uppdelad arbetsstruktur**.
4.  Klicka på **Nytt** om du lägger till följande aktiviteter för första nivån till strukturen:
    -   Påbörjande
    -   Planering
    -   Kör
    -   Övervakning och kontroll
    -   Stäng

5.  Ange datum och insats (timmar), som i följande skärmdump[![Ange datum och insats](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)
6.  Välj uppgiftsraden **Initierande** och sedan, i fältet **Roll**, välj **Senior projektledare**.
7.  Klicka på **Publicera**.
8.  På samma rad, i fältet **Resurs**, välj **Daniel Goldschmidt**.
9.  Klicka på **Godkänn**.
10. Välj **Planering**-uppgiftsraden och sedan, i fältet **Roll**, välj **Affärsanalytiker**.
11. Klicka på **Publicera** och klicka sedan på **Autogenerera team**.
12. Klicka på **Ja** i dialogrutan som visas.
13. I fältet **Resurs**, kontrollera att värdet är **Affärsanalytiker 1**.
14. För resursen **Affärsanalytiker 1**, öppna sökningen och klicka på **Starta formulär för resurstilldelning**.
15. Välj en arbetare för uppgiften.
16. Klicka på **Preliminär tilldelning** &gt; **Total kapacitet**.
17. Klicka på **Spara** och stäng sidan. 

> [!NOTE] 
> Du får inte en varning om att den angivna resursen nu är 2, eftersom antalet resurser återstår på 1.
18. På sidan **Uppdelad arbetsstruktur**, validera resurstilldelningen för strukturen och klicka sedan på **Spara**.

## <a name="resource-fulfillment-for-planned-resources"></a>Resursuppfyllelse för planerade resurser
En projektledare kan planera obligatoriska resursroller för ett projekt. Resurschefen ser dessa planerade resurser som förfrågningar på **Resursuppfyllelse**-sidan och kan tilldela verkliga resurser.

1.  Klicka på **Projekthantering och redovisning** &gt; **Projekt** &gt; **Alla projekt**.
2.  I listan, välj projektet **XYZ uppgraderingsfas 2**.
3.  Klicka på **Projekt**.
4.  Klicka på **Redigera**.
5.  På fliken **Projektteam och tidsplanering**, ** ** klicka på **Lägg till**.
6.  I **Lägg till roller**-dialogrutan, välj rollen **Programutvecklare**.
7.  Klicka på **Skapa**.
8.  Stäng projektsidan.
9.  Klicka på **Projekthantering och redovisning** &gt; **Projektresurser** &gt; **Resursuppfyllelse**.
10. Välj **Programutvecklare 1** för projektet **XYZ uppgraderingsfas 2**.
11. Välj en arbetare och klicka sedan på **Tilldela**.
12. Kontrollera att raden för **Programutvecklare 1** har raderats för projektet **XYZ uppgraderingsfas 2**.
13. På fliken **Projektteam och tidsplanering**, för projektet **XYZ uppgraderingsfas 2**, verifiera att arbetaren du valde i steg 11 har lagts till som **Programutvecklare**.

## <a name="requests-for-project-resources"></a>Förfrågningar om projektresurser
Schemaläggningsfunktionen projektresurser stöder bara resursansvariga för att distribuera bemannade resurser för åtaganden eller projekt. För att aktivera funktionen slutför du följande uppgifter, eller kontrollera att de har slutförts.

-   Ställa in nummerserier.
-   Ställ in projekthanterings- och redovisningsarbetsflöden.
-   Aktivera arbetsflödet för resursbegäran.

När du har kontrollerat eller slutfört de ovanstående uppgifterna kan du slutföra följande uppgifter efter behov.

-   Skapa en resursbegäran från en preliminärbokad bemannad resurs.
-   Övervaka resursbegäranden.
-   Uppfylla resursbegäranden.
-   Begära en bemannad resurs från struktur.
-   Boka resurser till ett projekt utan en begäran om en bemannad resurs.

## <a name="monitor-project-teams"></a>Övervaka projektteam
1.  Klicka på **Projekthantering och redovisning** &gt; **Projekt** &gt; **Alla projekt**.
2.  I listan för projekt, klicka på länken **Projekt-ID** för projektet **XYZ uppgraderingsfas 2**.
3.  På snabbfliken **Projektteam och tidsplanering**, verifiera att de listade projektresurserna är korrekta.





