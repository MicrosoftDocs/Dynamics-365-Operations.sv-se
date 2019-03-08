---
title: Resurshantering för projekt
description: Det här avsnittet innehåller information om resurshantering för projekt.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 34f80d283bb710d7db3137a439dbe8dc67d22682
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "351664"
---
# <a name="project-resourcing"></a>Resurshantering för projekt

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om resurshantering för projekt.

En utmaning för projektledare och resurschefer under projektplanläggningsfasen är resursallokeringen, där de måste bestämma och reservera rätt resurser för arbetet i ett projekt. I Microsoft Dynamics 365 for Finance and Operations resurshanteringsfunktioner för projekt kan du definiera roller som behandlas som tillfälliga resurser, som kan reserveras för ett visst engagemang eller delar av ett engagemang. Den här typen av resurshantering låter projektledare och resurschefer slutföra följande uppgifter:

- Definiera en roll som har begärt kompetenserna, så blir det enkelt att matcha resurser.
- Använd roller för att definiera en ursprunglig engagemangstidsplan som baseras på reserverade resurser.
- Beräkna kostnader och konfigurera en ursprunglig budget baserad på tilldelade roller och resurser för ett projekt.
- Använd roller för att beräkna antalet resursreserveringar som krävs för respektive engagemang.
- Beräkna antalet resurser som krävs för hela livscykeln för ett projekt.
- Gör ett utkast till en uppdelad arbetsstruktur med hjälp av de ursprungliga resurstilldelningarna.

[![Projektets livscykel](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg)

I takt med att projektplanläggningen fortsätter, kan planerade resurser ersättas med bemannade resurser. Projektledaren kan också gå tillbaka och uppdatera resursreservationerna under samtliga projektfaser.

## <a name="set-up-project-resources"></a>Ställ in projektresurser
Du måste ställa in en kalender och associera den till en medarbetare eller en arbetare. Kalendern används för att kunna tidsplanera projektet och arbetstiden för de resurser som har reserverats för projektet. Under kalenderinställningarna kan projektledare kan utföra resursutjämning som en del av resursoptimeringen. Baserat på kalendertidsplanen kan begränsningar tillämpas på resurser. Du kan ställa in en kalender på sidan **Kalendrar**.

När du konfigurerar en medarbetare som e projektresurs kan du välja bland medarbetare som arbetar på det företag som du konfigurerar resurser för. Alternativt kan du välja medarbetare från andra företag inom din organisation. Dessa medarbetare kallas även företagsinterna resurser.

Följande procedurer förklarar hur du konfigurerar en medarbetare som en projektresurs inom ditt företag samt hur du konfigurerar en företagsintern projektresurs.

### <a name="set-up-a-worker-as-a-project-resource"></a>Ställ in en arbetare som en projektresurs

1. På sidan **Arbetare**, i listan **Arbetare**, välj den arbetare som du lägger till som en projektresurs och öppna arbetarens post.
2. I åtgärdsfönstret markerar du **Projekt** &gt; **Inställningar** &gt; **Projektinställning**.
3. Välj en kalender och stäng sedan sidan.

Du kan även ange standardprojekt för en resurs som en typ av förtilldelning. Förtilldelningar kan användas när resurschefen eller projektledaren vet vilka projekt att resursen ska arbeta med i förväg. Förtilldelningar kan också baseras på en begäran av en projektsponsor eller kund. Du förtilldelar ett projekt genom att välja lämpligt projekt på sidan **Tilldela projekt**, på **Projekt** fliken, i listan **Resterande projekt**.

### <a name="set-up-an-intercompany-resource"></a>Ställa in en koncernintern resurs

När du ställer in en medarbetare som en företagsintern resurs måste du slutföra inställningarna i både det långivande företaget och det lånande företaget.

**I det långivande företaget**

1. I Finance and Operations kontrollerar du att det långivande företaget har valts och slutför sedan proceduren i föregående avsnitt, "Ställ in en medarbetare som en projektresurs".
2. På sidan **Företagsintern redovisning** markerar du **Ny**.
3. I fältet **ID för juridisk person** markerar du det långivande företaget. Fyll i återstående fält efter behov och markera sedan **Spara**.
4. På sidan **Överföringspris** markerar du **Ny**.
5. I fältet **Lånande juridisk person** markerar du lämpligt företag.
6. Om du endast vill låna den resurs som du skapa de i början av detta avsnitt till det lånande företaget, markerar du namnet på den resurs som du skapat i fältet **Resurs**. Om du vill att alla resurser inom företaget som lånar ut ska vara tillgängliga för företaget som lånar, lämnar du fältet **Resurs** tomt.
7. På sidan **Projekthantering och redovisningsparametrar**, på fliken **Företagsintern**, anger du alternativet **Aktivera företagsintern resursplanering och tidrapporter** som **Ja**.

**I det lånande företaget**

- I sökfiltret på sidan **Resurslista** anger du namnet på den resurs som du skapade för företaget som lånar ut, detta i syfte att bekräfta att namnet inkluderas i resurslistan för företaget som lånar.

## <a name="manage-resource-competencies"></a>Hantera resurskompetenser
Resurskompetenser är en viktig del av resurshantering. Kompetenser kan användas som en jämföra för att bestämma resurser som har rätt balans av utbildning, färdigheter, certifiering och projekterfarenhet. Du bör ställa in informationen för varje resurs och uppdatera den regelbundet. På så sätt kan du maximera förmågor när specifika resurskompetenser matchas under projektresurstilldelning.

[![Exempel på färdigheter, certifieringar, utbildning och projekterfarenhet](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg)

Följande procedurer innehåller information om hur du ställer in vissa kompetenser för en resurs.

Om du vill ställa in kompetenser för en arbetare kan du använda antingen **Arbetare** listsidan i Personal eller **Resurser** listsidan i Projekthantering och redovisning. För följande procedurer används listsidan **Arbetare** i Personal.

### <a name="set-up-competencies-certificates"></a>Ställa in kompetenser: Certifikat

1. På listsidan **Arbetare** markerar du raden för den medarbetare som du lägger till certifikatinformation för.
2. I Åtgärdsfönstret, på fliken **Arbetare**, i gruppen **Kompetenser**, markerar du **Certifikat**.
3. Markera **Ny** och sedan, i fältet **Certifikatstyp**, markerar du **PMP**.
4. I fältet **Startdatum** markerar du **10/1/2015** och sedan **spara**.

### <a name="set-up-competencies-skills"></a>Ställ in kompetenser: Kompetenser

1. Kontrollera på listsidan **Arbetare** att arbetaren som du använde i den föregående proceduren markeras fortfarande. I åtgärdsfönstret, på fliken **Arbetare**, i gruppen **Kompetenser**, markerar du sedan **Kompetenser**.
2. Markera **Nytt**.
3. I fältet **Kompetens**, välj **Projekthantering**.
4. I fältet **Nivå**, välj **5 Expert**.
5. I fältet **Nivådatum**, välj **1-/14/2014**.
6. Ange i **Erfarenhetsår** fältet, **10**.
7. Markera **Spara** och stäng sedan sidan.

## <a name="create-a-new-project"></a>Skapa ett nytt projekt
1. På sidan **Projekthantering** markerar du **Nytt projekt** och anger sedan följande värden:

    - **Projekttyp:** tid och material
    - **Projektnamn:** XYZ uppgraderingsfas 2
    - **Projektgrupp:** TM\_WIP
    - **Projektkontrakt-ID:** 00000002

2. Markera **Skapa projekt**.

### <a name="assign-a-resource-to-a-project"></a>Tilldela en resurs till ett projekt

1. På sidan **Arbetare**, på listan **Arbetare**, markerar du posten för den medarbetare som du tidigare angett kompetenser för, och öppnar sedan arbetarposten.
2. I Åtgärdsfönstret, på fliken **Projekt**, i gruppen **Inställningar**, markerar du **Tilldela projekt**.
3. På sidan **Projekttilldelningar för resursvalidering**, på fliken **Projekt**, i fältet **Lägg till projektet bland valda projekt**, filtrera projektet **XYZ-uppgradering fas 2**.
4. I fönstret **Återstående projekt**, markera ett projekt och markera sedan pilknappen för att lägga till det i fönstret **Valda projekt**.

Du kan vid behov också tilldela kategorier för en resurs. Kategoritypen är antingen **Kostnad** eller **Intäkt**. Kategoritypen bestäms av din organisation. Om det inte finns några tilldelade kategorier för en resurs, slår Finance and Operations upp standardkategorin på timpriser för kostnader och intäkter.

### <a name="set-up-project-resource-and-role-characteristics"></a>Ställ in projektresurs och rollegenskaper

En projektledare kan använda projektresurshanteringsfunktionen för att skapa roller som krävs för projektet. Roller kan användas om bekräftade resurser fortfarande är okända när resurser reserveras. Roller kan tillfälligt reserveras som planerade resurser, så att du kan fortsätta projektplanläggningsfaserna.

[![Exempel på en roll](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scenario:** Contoso anlitades för att slutföra ett tids- och materialprojekt som har ett godkänt projektramverk. Juniorprojektledaren avslutar fortfarande omfånget för projektet. Den resursansvarige identifierar för närvarande specifika resurser som ska reserveras för arbete på det nya projektet. På grund av projektets vitala natur har projektets sponsor begärt rollen som ledande projektchef som en av sina roller. Resursansvarig måste anskaffa den nya resursen och definiera rollen i systemet om biträdande projektledare behöver resursinformationen i samband med projektplaneringen.

Följande steg visar hur resursansvarig kan ställa in rollen Seniorprojektledare och associera resursegenskaper med den. Senare rollen kan användas för att söka efter tillgängliga resurser som matchar de nödvändiga resurskompetenserna.

1. På sidan **Konfigurera roller** markerar du **Nytt** och anger sedan följande värden:

    - **Roll ID:** Senior projektledare
    - **Beskrivning:** Senior projektledare

2. Markera **Skapa**.
3. Markera rollen **Senior Project Manager** och markera sedan **Konfigurera egenskaper**.
4. I fältet **Egenskapstyp**, välj **Kompetens**.
5. I fältet **Tillgängliga egenskaper** anger du den kompetens som du söker efter.
6. I fältet **Egenskapstyp**, välj **Certifikat**.
7. I fältet **Tillgängliga egenskaper**, ange den certifikattyp som du söker efter.

### <a name="assign-a-project-resource-to-a-project"></a>Tilldela en projektresurs till ett projekt

1. På sidan **Alla projekt** markerar du projektet **XYZ-uppgradering fas 2**.
2. På fliken **Projektteam och tidsplanering** markerar du **Lägg till**.
3. I fältet **Roll**, välj **Teammedlem**.
4. Markera **Boka via kalender**.
5. På sidan **Resurstillgänglighet** markerar du **Visa inställningar**.
6. På sidan **Justera visningsinställningar**, ange följande värden:

    - **Vy för format för datumintervall:** Dag
    - **Visa beskrivningar av tillgänglighet:** Ja
    - **Visa resterande kapacitet:** Ja

7. Välj en resurs i listan över resurser.
8. Markera **Fast bokning** och **Full kapacitet**.


### <a name="assign-a-resource-to-a-default-role"></a>Tilldela en resurs till en standardroll

Om du vill hjälpa projektledare eller resursansvariga kan du ytterligare fördjupa dig i resurserna som kan reserveras för ett projekt. Du kan associera en standardroll med en befintlig resurs eller en nyligen anskaffad resurs. Exempelvis när Daniel anställdes hade han erfarenhet och sakkunskap som passade för rollen Affärsanalytiker. Resursansvarige tilldelade den här rollen som Daniels standardroll. Därefter lade resursansvarige till Daniel i en pool med affärsanalytiker som är tillgängliga för arbete i projekt.

Under resursreserveringen kan projektledare filtrera rollresurserna som är tillgängliga för arbete i projekt. De kan använda den här informationen som ett villkor när de använder beslutsanalys för flera kriterier under resursuppfyllelse. De kan också lägga till andra resursegenskaper till filtret om du vill söka efter resurser som har specifika färdigheter, utbildning och erfarenheter för ett visst projekt.

**Scenario:** Ett godkänt projekt har startat och den seniora projektledarrollen reserverades som en planerad resurs under projektplanläggningsfasen. Resurschefen har nu fått en resurs för att uppfylla den seniora rollen som projektledare.

1. På sidan **Resurslista** markerar du **Daniel Goldschmidt**.
2. På sidan **Resursroll** markerar du **Nytt** och anger sedan följande värden:

    - **Giltighet:** Ange aktuellt datum.
    - **Utgår:** Ange **Aldrig**.
    - **Roll:** Ange **Senior Project Manager**.

3. Markera **Spara** och stäng sedan sidan.
4. På fliken **Kompetenser**, lägg till färdigheten **ProjectMgmt** och **PMP**.

## <a name="set-up-role-based-pricing"></a>Ställ in rollbaserad prissättning
Alla kostnader, försäljningar och internpriser kan ställas in för roller.

1. På sidan **Försäljningspris (timme)** markerar du **Nytt**, och anger ett giltighetsdatum.
2. Välj en roll i kolumnen **Roll**.
3. I kolumnen **Priser**, ange ett pris för den valda resursrollen.

## <a name="form-a-project-team"></a>Skapa ett projektteam
Om du vill använda de roller som redan har ställts in i ett projekt, måste en projektledare associera rollerna med projektet. Flera roller kan tilldelas för ett projekt. I syfte att undvika förvirring märker Finance and Operations automatiskt dessa roller under reservation. Om till exempel projektledaren kräver tre programingenjörer, genereras automatiskt tre roller för programingenjör som har etiketterna **programingenjör 1**, **programingenjör 2** och **programingenjör 3**. Om rollen tidigare fått egenskaper, används de som ett filter för sökningar efter en resurs. Ytterligare egenskaper kan läggas till som krävs för att begränsa sökningen.

Visningsinställningar kan också anpassas för att ge en bättre vy av resurstillgänglighet. Det finns alternativ för att visa tim, dag, vecka, månad, kvartalsvis och årlig tillgänglighet. Det finns även alternativ för att visa återstående och tillgänglig kapacitet för resurser. Det här alternativet är användbart för tidsadministration, när du vill beräkna tillgänglig tid för aktiviteter eller resurstillgänglighet.

Projektledaren kan välja en roll på sidan och sedan, om det finns en tillgänglig resurs som passar behovet, välja att reservera en resurs för att fylla rollen. Observera att resurserna inte måste reserveras vid denna tidpunkt i planeringsfasen. När du skapar en struktur kan du ersätta roller med bemannade resurser för projektet. Om roller ersättas med bemannade resurser i strukturen uppdaterar inställningen av resursen automatiskt projektteamslistan och tidsplaneringen.

[![Projektteam som innehåller både roller och faktiska resurser](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Projektchefen har olika alternativ för att boka resurser för ett projekt, till exempel **Resterande kapacitet**, **Total kapacitet**, **Kapacitet i procent** och **Ange timmar**. Dessa bokningsalternativ kan annulleras när som helst om resurstilldelningen ändras. Två typer av bokningar stöds:

- **Fast bokning** – Resursreservationen godkändes och bekräftades för att arbeta på engagemanget under den angivna varaktigheten.
- **Preliminär bokning** – Resursreservationerna godkändes preliminärt för att arbeta på engagemanget för den angivna varaktigheten.

Följande procedur förklarar hur du skapar ett projektteam.

### <a name="create-a-project-team"></a>Skapa ett projektteam

1. På listsidan **Alla projekt**, markera ett projekt och markera sedan **Redigera**.
2. På fliken **Projektteam och tidsplanering**, i fältet **Schemalagt slutdatum**, ange schemastartdatumet plus en månad. Om till exempel schemastartdatumet är 24 juni 2017 (24/06/2017), ange **24/07/2017**.
3. Markera **Lägg till**.
4. I **Lägg till roller i projektet**-fönstret, i **Roll**-fältet, välj **Senior projektledare**.
5. Markera **Erforderliga kompetenser**.
6. På **Välj egenskaper**-sidan markeras de egenskaper som du tidigare angett för rollen senior projektledare som standard. Välj **OK**.
7. På **Lägg till roller i projektet**-sidan i **Antal resurser**-fältet, ange **1**.
8. I **Resurs**-fältet visar sökningen alla resurser som har begärt kompetenserna. Markera **Daniel Goldschmidt** och markera sedan **Skapa**.
9. På sidan **Projekt** markerar du **Lägg till**.
10. I **Lägg till roller i projektet**-fönstret, i **Roll**-fältet, välj **Teammedlem**. I fältet **Antal resurser**, ange **5**.
11. Markera **Skapa**.
12. På sidan **Projekt** markerar du **Uppfyll resurs**.

## <a name="resource-capacity-synchronization"></a>Synkronisering av resurskapacitet
Processerna för synkronisering av resurser hjälper till att garantera att information till kalendern och baskalendern sipprar ned i tidsplaneringen av projektresurser. Om kalendern ändras gör processerna de nödvändiga uppdateringarna av planeringen av projektresurser. Processerna kan även förbättra prestanda, detta eftersom resursinformationen i kalendern synkroniseras i förväg. Därför sker uppdateringar för resursplaneringsinformation snabbare. Vi rekommenderar att du planerar processer som en batch i stället för en i taget. Annars finns det en risk att någon glömmer inklusive datum när informationen synkroniserades senast. Om inklusive datum inte används, luckor kan inträffa under datumsynkronisering.

![Kalendersynkronisering](./media/projectresourcing04-1024x471.jpg)

### <a name="synchronize-resource-capacity-roll-ups"></a>Synkronisera kapacitetsuppföljningar för resurs

Synkroniseringsprocessen har utformats för att synkronisera all information om resurskalendrarna. Informationen omfattar baskalenderinformation om alla ändringar i kapacitetsregistret för projektets resurskalender. Om nya resurser läggs till i projektet, synkroniseringen hjälper till att garantera att den uppdaterade kalenderinformationen är tillgänglig. Den här synkroniseringen kan göras när som helst.

Vi rekommenderar att du använder en batch. Alternativen är tillgängliga i samband med synkronisering av kapacitetsreservationer.

1. Markera **Projekthantering och redovisning** &gt; **Periodisk** &gt; **Kapacitetssynkronisering** &gt; **Synkronisera kapacitetsuppföljningar för resurs**.
2. I följande tabell ställer du in alternativen.

    | Alternativ      | beskrivning |
    |-------------|-------------|
    | Periodkod | Markera vid behov datumintervallkod Redovisning för att ange start- och slutdatum för synkroniseringen av resurskapacitetssummeringen. |
    | Startdatum  | Ange startdatum för synkroniseringen för resurskapacitetssummeringen. |
    | Slutdatum    | Ange slutdatum för synkroniseringen för resurskapacitetssummeringen. |

[![Synkroniseringsprocess](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Konfigurera roller för strukturmallar
Projektledare kan ställa in strukturmallar de kan använda när de skapar en struktur för nya projekt. Projektledare kan lägga till roller när de skapar en mall. Använd följande procedur för att tilldela en roll till en strukturmall. 

1. Markera **Projekthantering och redovisning** &gt; **Inställningar** &gt; **Projekt** &gt; **Uppdelade arbetsstrukturmallar**.
2. Markera **Information** för en vald strukturmall.
3. Välj en uppgift i listan och sedan, i **Roll**-fältet, välj en roll som ska tilldelas uppgiften.

### <a name="work-with-a-wbs"></a>Arbeta med en struktur

Du kan skapa en ny struktur, eller så kan du kopiera en struktur från en befintlig strukturmall. En projektledare kan enkelt hantera resurserna genom att tilldela roller till nya uppgifter på strukturen. Roller kan ersättas antingen efter det att en resurs har anskaffats eller efter det att en bekräftad resurs som ska arbeta med uppgiften identifierats. Denna flexibilitet låter projektledare utföra följande uppgifter:

- Identifiera det antal resurser som krävs för strukturarbetspaket.
- Uppskatta projektkostnader.
- Fastställa en preliminär budget.
- Beräkna aktivitetvaraktighet baserat på roller och resurser.
- Utveckla alla projektledningsplaner baserat på den tillgängliga projektinformationen.

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
<td>Automatiskt lägg till planerade resurser genom att använda roller som associeras med en uppgift. Finance and Operations föreslår automatiskt planerade resurser genom att använda beslutsanalys för flera kriterier baserat på roller. När rollerna och insatsen (timmar) har angetts för uppgifterna i en struktur, samt efter det att strukturen har frisläppts, markerar du <strong>Autogenerera team</strong>. Det begärda antalet planerade resurser läggs till i strukturen och på fliken <strong>Projekt och tidsplanering av team</strong>.</td>
</tr>
<tr class="odd">
<td>Resurs (listruta)</td>
<td>På sidan <strong>Starta resurstilldelning</strong> kan du välja resurser att preliminär- eller fastboka utifrån den angivna varaktigheten. Du kan justera vyinställningarna om du vill visa och ange längden för resursaktiviteter. Du kan välja och tilldela resurser på nivån för arbetspaketet genom att använda följande alternativ:
<ul>
<li><strong>Godkänn</strong> – Bekräfta ändringarna för resursen som har tilldelats en uppgift.</li>
<li><strong>Avbryt</strong> – Avbryt ändringarna för resursen som har tilldelats en uppgift.</li>
<li><strong>Tilldela automatiskt</strong> – En tillgänglig bemannad resurs med en matchande roll väljs automatiskt och tilldelas till den valda uppgiften.</li>
</ul></td>
</tr>
</tbody>
</table>

1. På sidan **Alla projekt** markerar du projektet **XYZ-uppgradering fas 2**.
2. Markera **Plan** &gt; **Aktiviteter** &gt; **Uppdelad arbetsstruktur**.
3. Markera **Nytt** för att lägga till följande aktiviteter för första nivån i strukturen:

    - Påbörjande
    - Planering
    - Kör
    - Övervakning och kontroll
    - Stäng

4. Ange datum och arbete (timmar) enligt följande illustration.

    [![Ange datum och arbete](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Välj uppgiftsraden **Initierande** och sedan, i fältet **Roll**, välj **Senior projektledare**.
6. Markera **Publicera**.
7. På samma rad, i fältet **Resurs**, markerar du **Daniel Goldschmidt** och sedan **Godkänn**.
8. Välj **Planering**-uppgiftsraden och sedan, i fältet **Roll**, välj **Affärsanalytiker**.
9. Markera **Publicera** och sedan **Autogenerera team**.
10. Markera **Ja** i meddelanderutan som visas.
11. I fältet **Resurs**, kontrollera att värdet är **Affärsanalytiker 1**.
12. För resursen **Affärsanalytiker 1**, öppna sökningen och markera **Starta resurstilldelning**. Markera sedan en medarbetare för uppgiften.
13. Markera **Preliminär tilldelning** &gt; **Total kapacitet**.

    > [!NOTE] 
    > Du får ingen varning om att den angivna resursen nu är 2, detta eftersom antalet resurser förblir 1.

14. På sidan **Uppdelad arbetsstruktur** validerar resurstilldelningen för strukturen och väljer sedan **Spara**.

## <a name="resource-fulfillment-for-planned-resources"></a>Resursuppfyllelse för planerade resurser
En projektledare kan planera obligatoriska resursroller för ett projekt. Resurschefen ser dessa planerade resurser som förfrågningar på **Resursuppfyllelse**-sidan och kan tilldela verkliga resurser.

1. På sidan **Alla projekt** markerar du projektet **XYZ-uppgradering fas 2**.
2. Markera **Projekt** och sedan **Redigera**.
3. På fliken **Projektteam och tidsplanering** markerar du **Lägg till**.
4. I **Lägg till roller**-dialogrutan, välj rollen **Programutvecklare**.
5. Markera **Skapa** och stäng sedan projektsidan.
6. På sidan **Uppfyllande av resurs** markerar du **Programutvecklare 1** för projektet **XYZ-uppgradering projektfas 2**.
7. Markera en medarbetare och markera sedan **Tilldela**.
8. Kontrollera att raden för **Programutvecklare 1** har raderats för projektet **XYZ uppgraderingsfas 2**.
9. På fliken **Projektteam och tidsplanering** för projektet **XYZ-uppgraderingsfas 2** verifierar du att medarbetaren du valde i föregående steg har lagts till som **Programutvecklare**.

## <a name="requests-for-project-resources"></a>Förfrågningar om projektresurser
Schemaläggningsfunktionen för projektresurser låter endast resursansvariga distribuera bemannade resurser för åtaganden eller projekt. För att aktivera funktionen slutför du följande uppgifter eller bekräftar att de har slutförts:

- Ställa in nummerserier.
- Ställ in projekthanterings- och redovisningsarbetsflöden.
- Aktivera arbetsflödena för resursbegäran.

När föregående uppgifter har slutförts kan du slutföra följande uppgifter efter behov:

- Skapa en resursbegäran från en preliminärbokad bemannad resurs.
- Övervaka resursbegäranden.
- Uppfylla resursbegäranden.
- Begära en bemannad resurs från en struktur.
- Boka resurser till ett projekt utan någon begäran om en bemannad resurs.

## <a name="monitor-project-teams"></a>Övervaka projektteam
1. På sidan **Alla projekt**, markera länken **Projekt-ID** för projektet **XYZ-uppgradering fas 2**.
2. På snabbfliken **Projektteam och tidsplanering**, verifiera att de listade projektresurserna är korrekta.
