---
title: Buntar för intäktsredovisning
description: I det här avsnittet beskrivs den buntfunktion som ingår i intäktsredovisningsfunktionen i kundreskontra. En bunt består av en överordnad artikel och flera komponentartiklar.
author: kweekley
manager: aolson
ms.date: 01/04/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: cf4d03c1a697259899c419ce084b35f4eddf13fe
ms.sourcegitcommit: bd53794cb94f8c1ce29a7d6102119a0975f155e3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "5142309"
---
# <a name="revenue-recognition-bundles"></a>Buntar för intäktsredovisning

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs den buntfunktion som ingår i intäktsredovisningsfunktionen i kundreskontra. En bunt består av en överordnad artikel och flera komponentartiklar. Den överordnade artikeln registreras på en försäljningsorder, så att orderregistreringen blir mer effektiv. Den bryts emellertid sedan ned i komponentartiklarna. Interna dokument, till exempel följesedeln, listar komponentartiklarna. Externa dokument visar dock bara den överordnade artikeln.

> [!NOTE]
> Microsoft Dynamics 365 Commerce-kanaler, som online, kassa och kundcenter, har inte stöd för intäktsredovisning (inklusive buntfunktionen). Det innefattar även lösningen Potentiell kund till kontanter för Dynamics 365 Supply Chain Management och Dynamics 365 Sales. Artiklar som har konfigurerats för att använda intäktsredovisning ska inte läggas till på order eller transaktioner som skapas i Commerce-kanaler eller i lösningen Potentiell kund till kontanter.

Om du vill konfigurera buntar måste du ange konfigurationsnycklar för intäktsredovisning. Du kan emellertid använda buntar även om intäktsredovisning inte har konfigurerats. Men du kan intäktsredovisning även om buntar inte har konfigurerats. Om intäktsredovisning har konfigurerats, bestämmer komponentartiklarna intäktspriset och intäktsplanen som används för intäktsredovisning eller periodisering när en försäljningsorder faktureras.

Konfigurationen för buntar använder funktionen för strukturlistor. Information om hur du konfigurerar en buntartikel finns i [inställningar för intäktsredovisning](revenue-recognition-setup.md). Om den överordnade artikeln flaggas som en bunt behandlas den på ett annat sätt än andra strukturlisteartiklar. Här är en lista över skillnaderna:

- Buntar måste brytas ned genom bekräftelse av försäljningsordern genom att du väljer **Bekräfta försäljningsorder** på fliken **Sälj** i åtgärdsfönstret på försäljningsordersidan. Du får aldrig bryta ned buntartiklar genom att markera **Strukturlisterad** under **Bryt ned** på menyn **Försäljningsorderrad** på snabbfliken **Försäljningsorderrad**. Annars behandlas artikeln som en strukturlista och inte som en bunt.
- En försäljningsorder som innehåller en buntartikel måste bekräftas innan följesedeln eller fakturan skapas.
- När en bunt bryts ned genom bekräftelse av försäljningsorder annulleras den överordnade artikeln och dess enhetspris och rabatter fördelas på buntens komponentartiklar.
- Summan av komponentartiklarna måste alltid vara lika med priset på den överordnade artikeln. Därför finns det begränsningar i fälten som kan uppdateras eller ändras för komponentartiklar. Enhetspriset kan till exempel inte ändras manuellt. Det kan inte heller ändras indirekt genom att ett nytt prisavtal gäller. Lagerdimensionerna kan inte ändras för komponentartiklarna för att förhindra ett nytt prisavtal.
- När ett externt dokument, till exempel försäljningsorderbekräftelsen eller fakturan skrivs ut, skrivs den överordnade artikeln ut, inte komponentartiklarna.

## <a name="bundles-on-sales-orders"></a>Buntar på försäljningsorder

Demonstrationsföretaget USMF innehåller följande buntinställningar. Observera att alla inställningar för intäktsredovisning, som inställningen av intäktsplanerna, har tagits bort från artiklarna som ingår i det här scenariot.

**Överordnad artikel:** Bunt för bärbar dator

- **Komponentartikel:** Kvantiteten 1 av artikel 1000
- **Komponentartikel:** Kvantiteten 1 av artikel S0021
- **Komponentartikel:** Kvantiteten 1 av artikeln Support

*Basförsäljningspriset* för komponentartiklarna är en viktig del av inställningarna för komponenterna. Basförsäljningspriset definieras på snabbfliken **Sälj** för en artikel. Den används för att beräkna allokeringsfaktorn när den överordnade artikelns enhetspris fördelas på komponentartiklarna. Handelsavtalsförsäljningspriserna används aldrig i det här syftet.

Följande basförsäljningspriser definieras för komponentartiklarna:

- **1000:** $1 900,00
- **S0021:** $150,00
- **Support:** $500,00

En försäljningsorder registreras för kunden US-004, Cave Wholesales. Den enda raden som registreras är för artikeln Bunt för bärbar dator. Standardpriset per enhet för den överordnade raden kan hämtas från flera platser, till exempel handelsavtalet eller basförsäljningspriset. I det här exemplet registreras 2 300 manuellt som enhetspris.

[![Artikeln Bunt för bärbar dator på en försäljningsorder](./media/bundle-01.png)](./media/bundle-01.png)

Eftersom försäljningsordern innehåller en bunt måste den bekräftas. I bekräftelsedialogrutan visas komponenterna i bunten.

[![Dialogrutan Bekräfta försäljningsorder som visar komponentartiklarna](./media/bundle-02.png)](./media/bundle-02.png)

Den utskrivna bekräftelserapporten visar dock endast den överordnade artikeln i bunten, eftersom rapporten är det externa dokumentet för kunden.

[![Bekräftelserapport som bara visar den överordnade artikeln](./media/bundle-03.png)](./media/bundle-03.png)

När försäljningsordern har bekräftats visas den överordnade artikeln fortfarande på försäljningsordern, men dess status har ändrats till **Annullerad**. Nettobeloppet spåras dessutom i fältet **Buntens nettobelopp**. Detta belopp krävs för att fakturan ska skrivas ut, eftersom fakturan visar den överordnade artikeln och inte komponentartiklarna.

Summan av komponentartiklarna måste vara lika med värdet **Buntens nettobelopp** för den överordnade artikeln, eftersom detta värde är det belopp som visas för kunden på den utskrivna fakturan. För att säkerställa att fakturan matchar beloppen som bokförs i redovisningen går det bara att redigera komponentartiklarna i begränsad utsträckning. Platsen och distributionslagret kan till exempel inte ändras eftersom dessa ändringar kan utlösa en prisändring baserat på ett handelsavtal.

Enhetspriset från raden för den överordnade artikeln fördelas på komponenterna på följande sätt:

**Totalt basförsäljningspris från komponenter:** $1 900 + $500 + $150 = $2 550

- **Komponent 1:** $2 ,300 × (1 900 ÷ 2 550) = $1 713,73
- **Komponent 2:** $2 300 × (500 ÷ 2 550) = $450,98
- **Komponent 3:** $2 300 × (150 ÷ 2 550) = $135,29

Summan av komponenterna måste vara lika med $2 300, och det gör ($1 713,73 + $450,98 + $135,29 = $2 300).

Om du behöver göra ändringar av alla komponentartiklar kan du ta bort den överordnade artikeln. I så fall tas även komponentartiklarna bort. Den överordnade artikeln kan sedan läggas till igen, och redigeringar kan göras innan försäljningsordern bekräftas.

[![Buntartikel som omfattar ändringar av komponentartiklarna](./media/bundle-04.png)](./media/bundle-04.png)

När försäljningsordern plockas och packas kommer dokumenten bara att innehålla komponenterna i bunten. Följesedeln och fakturan måste omfatta en hel bunt. Annars kan de inte bokföras. I dialogrutan visas till exempel tre komponentartiklar. Om du försöker ta bort en av dem visas ett felmeddelande om att alla produkter i bunten måste levereras innan de kan faktureras.

En bunt måste levereras och faktureras som en hel bunt. Om du till exempel ändrar kvantiteten för artikel 1000 till 4, men lämnar kvantiteten för de andra komponentartiklarna till 5, kan följesedeln och fakturan inte bokföras.

En delmängd kan bara levereras och faktureras om kvantiteten reduceras för alla komponenter i bunten. Exempel: Kvantiteten 5 av artikeln Bunt för bärbar dator registreras på en försäljningsorder. När försäljningsordern har bekräftats visas de tre komponentartiklarna på försäljningsordern och kvantiteten för var och en av dem är 5. Som standard sätts kvantiteten till 5 för varje komponent under leverans och fakturering. Du kan dock justera kvantiteten ned till 3 för alla tre komponentartiklarna. I det här fallet levereras och faktureras tre fullständiga buntar. De återstående två buntartiklarna (kvantiteten 2 av samtliga tre komponentartiklar) kan levereras och faktureras senare.

Det sista steget är att fakturera försäljningsordern. Under fakturering visas komponentartiklarna i dialogrutan Faktura.

[![Dialogrutan Faktura som visar komponentartiklarna](./media/bundle-06.png)](./media/bundle-06.png)

Den utskrivna fakturan visar dock bara den överordnade artikeln.
 
[![Utskriven faktura som bara visar den överordnade artikeln](./media/bundle-07.png)](./media/bundle-07.png)

Fakturajournalen som skapas efter bokföringen skapas inte med den överordnade artikeln från bunten eftersom artikeln har statusen **Annullerad**.

[![Fakturajournal som inte innehåller det överordnade objektet](./media/bundle-08.png)](./media/bundle-08.png)

Det är viktigt att fakturajournalen inte innehåller den överordnade artikeln från bunten, eftersom eventuella processer som utförs efter att fakturan har bokförts baseras på fakturajournalen. Om du till exempel skapar en kreditfaktura från fliken **Sälj** i åtgärdsfönstret, kommer kreditfakturan som skapas att inkludera komponentartiklarna men inte den överordnade artikeln.

[![Kreditfaktura som visar komponentartiklarna men inte den överordnade artikeln](./media/bundle-09.png)](./media/bundle-09.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]