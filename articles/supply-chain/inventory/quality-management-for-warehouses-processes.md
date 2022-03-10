---
title: Kvalitetsstyrning för lagerprocesser
description: Det här ämnet innehåller information om funktionen för kvalitetshantering för lagerprocesser. Den här funktionen utökar möjligheterna för kvalitetshantering och låter användarna integrera artikelsamplingskontroller i den process som tar emot lager med hjälp av avancerad Warehouse management.
author: Henrikan
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-02
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: d81441fcc8cb86927923e76bd1a4d16a141ddc75
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571891"
---
# <a name="quality-management-for-warehouse-processes"></a>Kvalitetsstyrning för lagerprocesser

[!include [banner](../includes/banner.md)]

Funktionen _Kvalitetshantering för lagerprocesser_ låter dig integrera artikelsamplingskontroller i den process som tar emot lager med hjälp av avancerad Warehouse management. Lagerställearbete kan skapas automatiskt för att flytta lagret till platsen för kvalitetskontroll, baserat på en procentsats eller en fast kvantitet, eller baserat på varje *n*-registreringsskylt. När en kvalitetsorder har slutförts kan arbetet skapas automatiskt för att flytta lagret till nästa plats i processen, beroende på kvalitets resultatet.

Funktionen _Kvalitetshantering för lagerprocesser_ omfattar alla funktioner i grundläggande kvalitetshanteringsfunktioner. Det ger möjlighet att skapa kvalitetsorder för lagret som skickas till kvalitetskontrollplatsen, även om kvalitetsorder inte alltid behövs. Därför möjliggörs en enkel kontrollprocess baserad på arbete på lager.

## <a name="turn-on-the-quality-management-for-warehouse-processes-feature"></a>Aktivera funktionen kvalitetshantering för lagerprocesser

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Warehouse management*
- **Funktionsnamn:** *Kvalitetshantering för lagerprocesser*

## <a name="key-benefits"></a>Viktiga fördelar

Funktionen _Kvalitetshantering för lagerprocesser_ genererar automatiskt arbete som en del av inleveransen, för att flytta lagerkvantiteten som krävs för kvalitetskontroll till en plats för kvalitetskontroll. Om den kvantitet som inlevereras överskrider den kvantitet som krävs för kvalitetskontroll (enligt artikelns samplingsinställning) flyttas det överskjutande antalet till en ankommande plats som definieras i inställningen för platsdirektiv. När kvalitetsordern har validerats genereras arbete automatiskt för att flytta kvantiteten för kvalitetsordern till en ny inlastningsplats eller returplats, baserat på valideringsresultatet och inställningen för platsdirektiv. Den automatiska genereringen av arbete som bara har den kvantitet som måste flyttas till och från kvalitetskontrollen är en integrerad processupplevelse.

> [!NOTE]
> När funktionen _Kvalitetshantering för lagerprocesser_ är aktiverad kan du ändå utnyttja den manuella processen. I den manuella processen används lagerrörelse och flyttning efter mall för att en lagerarbetare ska utlösa skapande av lagerarbete för att flytta lagret från en kvalitetskontrollplats till en ny plats. Du kan även ställa in ett inkommande platsdirektiv som flyttar hela lagret från en mottagningsplats till en kvalitetskontrollplats utan att ta hänsyn till inställningen av artikelsampling.

## <a name="quality-management-and-the-quality-management-for-warehouse-processes-feature"></a>Kvalitetshantering och funktionen Kvalitetshantering för lagerprocesser

När funktionen _Kvalitetshantering för lagerprocesser_ är aktiverad ändras konfigurationen av entiteter för viktig Warehouse management och kvalitetshantering. Följande illustration ger en översikt över de entiteter som aktiverar kvalitetsorder för lagerprocesser. Text inom parentes anger föreslagna åtgärder när kvalitetshanteringen tillämpades innan funktionen _Kvalitetshantering för lagerprocesser_ aktiverades.

![Entiteter för kvalitetshantering.](media/quality-management-entity-diagram.png "Entiteter för kvalitetshantering")

## <a name="enablers-the-quality-item-sampling-and-quality-order-work-order-types"></a>Förutsättningar: artikelsampling av kvalitet och arbetsordertyper för kvalitetsorder

Funktionen _Kvalitetshantering för lagerprocesser_ introducerar de två arbetsordertyper som aktiverar processen för skapande av arbete:

- **Artikelsampling av kvalitet** – den här arbetsordertypen används för att skapa arbete som flyttar registrerade lager till kvalitetskontroll.
- **Kvalitetsorder** – den här arbetsordertypen används för att skapa arbete som flyttar lager från kvalitetskontroll till en ny plats, baserat på inställningen för platsdirektiv.

### <a name="work-classes-location-directives-and-work-templates"></a>Arbetsklasser, platsdirektiv och arbetsmallar

Arbetsordertyperna _Artikelsampling av kvalitet_ och _Kvalitetsorder_ förbrukas av platsdirektiv, arbetsklasser och arbetsmallar.

Innan lagerarbete kan genereras automatiskt för att flytta lager till kvalitetskontroll måste du konfigurera systemet enligt följande instruktioner.

1. Skapa separata arbetsklasser för arbetsordertyperna _Artikelsampling av kvalitet_ och _Kvalitetsorder_. På så sätt ser du till att lämpligt arbete kan genereras automatiskt på grundval av de två arbetsordertyperna och att det här arbetet sedan kan köras med hjälp av mobilappen för distributionslagerhantering.
1. Ställa in en arbetsmall för varje arbetsordertyp:

    - Skapa en arbetsmall som använder arbetsordertypen _Artikelsampling av kvalitet_ för att automatiskt flytta registrerade lager till en plats för kvalitetskontroll.
    - Skapa en arbetsmall som använder arbetsordertypen _Kvalitetsprder_ för att flytta lager från en plats för kvalitetskontroll efter att en kvalitetskontroll utförs.

1. För varje arbetsordertyp ställer du in platsdirektiv som tillämpar rätt platser för kvalitetskontroll som lagret ska flyttas till. Efter att kvalitetskontrollen har slutförts säkerställer platsdirektivet för arbetsordertypen _kvalitetsorder_ att en ny destinationsplats väljs så att lagret kan flyttas från kvalitetskontrollplatsen.
1. Ställ in de relevanta menyalternativen för mobila enheter för att stödja flyttning av mottaget lager till kvalitetskontrollplatsen och lagerförflyttning som skickar eller underlåter en kvalitetskontroll från platsen för kvalitetskontroll till en ny plats.

Ett steg för steg-exempel som visar hur du utför den här inställningen, se [exempelscenariot](#example-scenario) i slutet av det här avsnittet.

## <a name="enable-a-warehouse-for-quality-management"></a>Aktivera ett lager för kvalitetshantering

Innan funktionen _Kvalitetshantering för lagerprocesser_ kan tillämpas för ett specifikt lager, måste du följa dessa steg för att göra funktionen tillgänglig för det lagret.

1. Gå till **Warehouse management \> Inställningar \> Lagerställe \> Lagerställen**.
1. Markera lagret för att aktivera kvalitetshantering.
1. På snabbfliken **lagerställe**, ange alternativet **aktivera kvalitetsorder för lagerprocesser** till _Ja_. (Observera att det här alternativet kan anges till _ja_ endast för lagerställen som använder lagerhanteringsprocesser.)

När alternativet **aktivera kvalitetsorder för lagerprocesser** anges till _ja_, inställningen för kvalitetsorder styr om funktionen _kvalitetshantering för lagerprocesser_ ansökte faktiskt om det valda lagerstället. Du kan ändra inställningen för alternativet till ingen _Nej_ när du vill. I så fall gäller inte längre funktionen för lagerstället, oberoende av inställningen för kvalitetsorder.

## <a name="quality-control"></a>Kvalitetskontroll

Funktionen _Kvalitetshantering för lagerprocesser_ kontrollerar flera viktiga inställningar för kvalitetsassociationer och artikelsamling.

### <a name="quality-associations"></a>Kvalitetsassociationer

Varje [kvalitetsassociationspost](enable-quality-management.md) definierar även testuppsättningarna, den godtagbara kvalitetsnivån och provtagningsplanen som gäller genererade kvalitetsorder. Så här ställer du in en kvalitetsassociationspost.

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Kvalitetsassociationer**.
1. Skapa eller välj en kvalitetsassociationspost för den artikel eller grupp som du arbetar med, eller för alla artiklar.
1. På snabbfliken **villkor** ställer du in fältet **Tillämplig lagerställetyp** på ett av följande värden:

    - **Kvalitetshantering för lagerprocesser** – Aktivera funktionen _kvalitetshantering för lagerprocesser_. Du kan bara välja det här värdet om referenstypen är antingen *inköp* eller *produktion*.
    - **Alla** – Inaktivera funktionen _Kvalitetshantering för lagerprocesser_. Välj det här värdet för alla referenstyper utom *inköp* och *produktion*.

> [!NOTE]
> Funktionen _Kvalitetshantering för lagerprocesser_ träder i kraft endast om objektet på källdokumentraden använder avancerade lagerhanteringsprocesser och om alternativet **aktivera kvalitetsorder för lagerprocesser** ställs in på _Ja_ för lager stället på källdokumentraden.

När varje artikel är registrerad (eller rapporterad som färdig) avgör systemet vilka kvalitetsassociationer som gäller för den.

När funktionen _Kvalitetshantering för lagerprocesser_ aktiveras sätts den tillämpliga lagertypen in logiskt i den fjärde sökgruppen i sökhierarkin för kvalitetsassociationer. Följande tabell ger en logisk representation av sökhierarkin.

| Sökgrupp | beskrivning |
|---|---|
| Grupp 1 | För varje kvalitetsassociation, kontrollera värdena **referenstyp**, **händelsetyp** och **körningsmatchning** mot artikeln. Om det finns en matchning mot källdokument raden går du vidare till grupp 2. |
| Grupp 2 | För varje kvalitetsassociation, kontrollera värdet **artikelkod** (_tabell_, _grupp_ eller _alla_) mot artikeln. _Register_ är mer specifikt än _grupp_ och _gruppen_ är mer specifik än _alla_. Om det finns en matchning för _register_ (en specifik artikel) går du vidare till grupp 3. Om det inte finns någon matchning för _register_, sök efter en matchning för _grupp_. Om det inte finns någon matchning _för_ gruppen _gäller_ alla. Om det finns en matchning går du vidare till grupp 3. |
| Grupp 3 | För varje kvalitetsassociation kontrollerar du värdena **kontokod** och **resurskod** mot artikeln. Den logik som används liknar den logik som används för värdet **artikelkod**. |
| Grupp 4 | För varje kvalitetsassociation, kontrollera värdet **Tillämplig lagerställetyp** (_Endast kvalitetshantering för lagerprocesser_ eller _Alla_) mot artikeln. Om alternativet **aktivera kvalitetsorder för lagerprocesser** anges till _Ja_ för lagerstället i källdokumentet, och artikeln på källdokumentraden är inställd på att _använd lagerhanteringsprocesser_, kommer båda associationer där det finns en matchning för _Endast kvalitetshantering för lagerprocesser_ och associationer där det är en matchning för _Alla_ kommer att tillämpas parallellt, om båda finns. Om alternativet **aktivera kvalitetsorder för lagerprocesser** anges till _nej_ för lagret på källdokumentet och objektet på källdokumentraden är inställt på _Använd lagerhanteringsprocessen_, endast kvalitetsstyrning kommer att tillämpas. |

Till exempel har du definierat ett lager där alternativet **aktivera kvalitetsorder för lagerprocesser** anges till _ja_ och du har två kvalitetsassociationer som har referenstypen *Inköp*: en för alla artiklar och en för händelstypen *Registrering*. Den enda skillnaden mellan de två kvalitetsföreningarna är värdet **Tillämplig lagerställetyp**: det anges till _Alla_ för en kvalitetsassociation och _Endast kvalitetshantering för lagerprocesser_ för den andra. I detta fall är båda kvalitetsassociationerna lika specifika och båda kommer att tillämpas.

Värdet i fältet **testgrupp** för kvalitetsassociationer är också en faktor. I det här fältet anges vilken testprocedur som måste tillämpas. Om **Testgrupp** är samma för båda associationer, endast en kvalitetsorder kommer att skapas för den kvalitetsassociation där värdet **Tillämplig lagerställetyp** är _Endast kvalitetshantering för lagerprocesser_. Om värdet **testgrupp** inte är identiskt för båda kopplingarna skapas två kvalitetsorder. Den första kvalitetsorder skapas för kvalitetsföreningen där värdet **Tillämplig lagerställetyp** är _Kvalitetshantering för lagerprocesser_. Den andra kvalitetsorder skapas för kvalitetsföreningen där värdet **Tillämplig lagerställetyp** är _Alla_.

> [!NOTE]
> Värdet _Endast kvalitetshantering för lagerprocesser_ anses vara mer specifikt än _Alla_ när kriterierna för kvalitetsföreningarna för grupperna 1 och 2 är desamma och när testgruppen är densamma. Två kvalitetsorder skapas bara när testgrupperna skiljer sig åt.

#### <a name="reference-types"></a>Referenstyper

När värdet **Referenstyp** är _Inköp_ och värdet **Tillämplig lagerställetyp** är _Endast kvalitetshantering för lagerprocesser_ måste fältet **Händelsetyp** på snabbfliken **Process** anges till _Registrering_. _Registrering_ är den enda händelsetyp som stöds för referenstypen _inköp_ när du använder funktionen _Kvalitetshantering för lagerprocesser_.

#### <a name="quality-processing-policy"></a>Policy för kvalitetsbearbetning

Med funktionen _Kvalitetshantering för lagerprocesser_ kan endast arbete skapas baserat på artikelsampling. Därför möjliggörs en lättviktig process. Lagret som arbete skapas i beror på artikelsamplingen som associeras med kvalitetsassociationen. När den lättviktiga processen används kan kvalitetsavdelningen, efter att en arbetare placerar kvantiteten på platsen för kvalitetskontroll, manuellt skapa en kvalitetsorder om det krävs en kvalitetsorder.

Fältet **Policy för kvalitetsbearbetning** på snabbfliken **Kvalitetsorderprocess** styr om en kvalitetsorder också skapas när arbetet skapas för att flytta ett objekt till platsen för kvalitetskontroll. Det här fältet kan bara anges till _Skapa kvalitetsorder_ eller _Skapa endast arbete_. Standardvärdet är _Skapa kvalitetsorder_.

> [!NOTE]
> Oavsett om du skapar kvalitetsorder manuellt eller automatiskt genererar systemet automatiskt arbete för att flytta artiklar från kvalitetskontrollplatsen när kvalitetsordern markeras som validerad.

Skapandet av kvalitetsorderarbete är inte relaterat till inställningen av kvalitetsassociationer. Om det finns en arbetsmall som har värdet **arbetsordertyp** på *kvalitetsorder* och om frågekriterierna uppfylls för den arbetsmallen kommer validering av en kvalitetsordning att utlösa skapandet av kvalitetsorderarbete.

#### <a name="referenced-item-sampling"></a>Refererad artikelsampling

Varje kvalitetsassociation måste referera till en artikelsampling. En artikelsampling anger den kvantitet som ska skickas för kvalitetskontroll. Det kan konfigureras så att det endast gäller kvalitetsassociationer där **Tillämplig lagerställetyp** är _Kvalitetshantering för lagerprocesser_. Om värdet **samplingsomfång** för en artikelsampling är _Last_ eller _Leverans_, eller om värdet **kvantitetspecifikation** är _full registreringsskylt_ kan artikelsamplingen endast refereras av kvalitetsassociationer där värdet är **Tillämplig lagerställetyp** är _Endast kvalitetshantering för lagerprocesser_.

Om du definierar en artikelsampling som använder den tillämpliga lagerställetypen _Endast kvalitetshantering för lagerprocesser_ kommer du att få ett fel om du försöker referera det från en kvalitetsassociation som inte använder funktionen _Kvalitetshantering för lagerprocesser_.

> [!NOTE]
> Artikelsampling som använder fullständig spärr stöds inte för kvalitetsassociationer där fältet **Tillämplig lagerställetyp** anges till _Endast kvalitetshantering för lagerprocesser_.

### <a name="item-sampling"></a>Artikelsampling

Artikelsampling styr hur ofta artiklar skickas för kvalitetskontroll. Funktionen _Kvalitetshantering för lagerprocesser_ omfattar konceptet av _artikelsamplingens omfång_. I systemet används artikel samplingsomfånget när det utvärderar om och hur kvalitetsorder och/eller kvalitetsartikelsampling och kvalitetsorderarbete ska skapas.

För att ställa in artikelsampling, gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Artikelsampling** och anger fältet **Samplingsområde** till ett av följande värden:

- **Order** – Källdokumentraden kommer att ligga till grund för att utvärdera huruvida och hur kvalitetsorder och/eller kvalitetsartikelsampling och kvalitetsorderarbete skapas. Detta värde är standardvärdet och när det är valt fungerar systemet på samma sätt som det fungerar när funktionen _Kvalitetshantering för lagerprocesser_ inte är aktiverad.
- **Last** – Last kommer att användas som bas för att utvärdera om och hur en kvalitetsorder och/eller arbete skapas. Det här värdet är bara tillgängligt om funktionen _Kvalitetshantering för lagerprocesser_ är aktiverad.
- **Försändelse** – Leveranser kommer att användas som bas för att utvärdera om och hur en kvalitetsorder och/eller arbete skapas. Det här värdet är bara tillgängligt om funktionen _Kvalitetshantering för lagerprocesser_ är aktiverad.

> [!NOTE]
> När fältet **Samplingsområde** anges till *Last* eller *Försändelse*, lastenheten och leveransenheterna kommer att användas om de är tillgängliga. Om de inte är tillgängliga kommer orderentiteten att användas.

Funktionen _Kvalitetshantering för lagerprocesser_ introducerar också värdet *Tillämplig lagerställetyp* för fältet **Kvantitetspecifikationen**. Det här värdet har stöd för generering av kvalitetsorderarbete och kvalitetsartikelsampling, baserat på registreringsskyltar. När du väljer det här värdet sker följande ändringar:

- Alternativet **Bryt räkna efter artikel** och fältet **Per N:te registreringsskylt** på snabbfliken **Process** blir tillgängliga.
- Fältet **Värde** på snabbfliken **Samplingskvantitet** blir inte tillgängligt.
- Alternativen **Per uppdaterad kvantitet**, **Plats** och **Registreringsskylt** är alla inställda på *Ja* och inställningarna kan inte ändras.

Alternativet **Bryt räkna efter artikel** styr om antalet registreringsskyltar utvärderas per artikel eller för alla artiklar i samplingsomfånget. Produktvarianter behandlas som samma artikel. Det här alternativet styr även om antalet registreringsskyltar återställs för varje artikel.

Värdet på fältet **per N:te registreringsskylt** styr hur ofta kvalitetsorder skapas i förhållande till antalet artiklar som registreras. Värdet *3* kommer till exempel att skicka var tredje objekt till kvalitetskontroll, med början på det första objektet. Värdet måste vara större än 0 (noll).

När arbetstagarna tar emot artiklar med hjälp av mobilappen för distributionslagerhantering, validerar systemet om en kvalitetsassociation har ställts in för varje inkommande artikel. Om en kvalitetsassociation har ställts in använder systemet den artikelsamplingspost som konfigurerats för den kvalitetsassociationen för att bestämma hur den ska skapa kvalitetsorder, sampling av kvalitetsartiklar och inköpsorderarbete.

> [!NOTE]
> När kvittoregistrering görs i webbklienten (med hjälp av den lilla registreringssidan eller artikel införsel journalen för inköpsorderrader), skapas inget artikelsamplingsarbete för kvalitet eller inköpsorderarbete, oavsett inställningarna. I stället används den refererade artikelsamplingen för artiklar som matchar en kvalitetsassociation för att styra skapandet av kvalitetsorder.

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Exempel på automatisk generering av kvalitetsorder

Följande exempel visar hur installationen av en kvalitetsförening och en tillhörande provtagning påverkar genereringen av kvalitetsorder när fältet **Tillämplig lagerställetyp** anges till _Endast kvalitetshantering för lagerprocesser_.

När värdet **kvantitetspecifikation** är _full registreringsskylt_, kontrollerar fältet **Per N:te registreringsskylt** vilka registreringsskyltar som kvalitetsartikelsampling skapas för. Den första registreringsskylten skickas alltid till kvalitetskontroll och sedan anger värdet i det här fältet att var och en av *N:te* registreringsskyltarna efter denna registreringsskylt också ska gå.

Värdet **Referenstyp** för följande exempel är _inköp_ och värdet för **händelsetyp** är *registrering*.

| Samplingsområde | Kvantitetsspecifikation | Per uppdaterad kvantitet | Per lagringsdimension | Antal brytningar per artikel | Per n:te registreringsskylt | Resultat |
|---|---|---|---|---|---|---|
| Order | Fullständig registreringsskylt | Ja _(låst/inte redigerbart)_ | <p>Plats: ja</p><p>ID-nummer: Ja _(låst/inte redigerbart)_</p> | Nej | 3 | <p>**Kvantitet på orderrad: 100 EA**</p><ol><li>Registrera inleverans i mobilappen för distributionslagerhantering för 20 EA, LP1<p>Sampling av kvalitetsartikel för 20 EA</p><p>Kvalitetsorder 1 för 20 EA</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för 20 EA, LP2<p>Arbete med inköpsorder på 20 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för 20 EA, LP3<p>Arbete med inköpsorder på 20 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för 20 EA, LP4<p>Sampling av kvalitetsartikel för 20 EA</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för 20 EA, LP5<p>Arbete med inköpsorder på 20 EA (artikelinförsel)</p></li></ol> |
| Order | Fast kvantitet = 1 | Ja | <p>Plats: ja</p><p>ID-nummer: ja</p> | Nej | Inte aktuellt | <p>**Kvantitet på orderrad: 100**</p><ol><li>Registrera inleverans i mobilappen för distributionslagerhantering för 20 EA, LP1<p>Sampling av kvalitetsartikel för 1 EA</p><p>Kvalitetsorder 1 för 1 EA</p><p>Arbete med inköpsorder på 19 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för 20 EA, LP2<p>Sampling av kvalitetsartikel för 1 EA</p><p>Kvalitetsorder 1 för 1 EA</p><p>Arbete med inköpsorder på 19 (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för 20 EA, LP3<p>Sampling av kvalitetsartikel för 1 EA</p><p>Kvalitetsorder 1 för 1 EA</p><p>Arbete med inköpsorder på 19 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för 20 EA, LP4<p>Sampling av kvalitetsartikel för 1 EA</p><p>Kvalitetsorder 1 för 1 EA</p><p>Arbete med inköpsorder på 19 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för 20 EA, LP5<p>Sampling av kvalitetsartikel för 1 EA</p><p>Kvalitetsorder 1 för 1 EA</p><p>Arbete med inköpsorder på 19 EA (artikelinförsel)</p></li></ol> |
| Order | Procent = 10 | Nej | <p>Plats: nej</p><p>ID-nummer: nej</p> | Nej | Inte aktuellt | <p>**Kvantitet på orderrad: 100 EA**</p><ol><li>Registrera inleverans i mobilappen för distributionslagerhantering för 50 EA, LP1<p>Sampling av kvalitetsartikel för 10 EA</p><p>Kvalitetsorder 1 för 10 EA</p><p>Arbete med inköpsorder på 40 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för 50 EA, LP2<p>Arbete med inköpsorder på 50 EA (artikelinförsel)</p></li></ol> |
| Last | Procent = 5 | Ja _(låst/inte redigerbart)_ | <p>Plats: nej</p><p>ID-nummer: nej</p> | Nej | Inte tillämpligt | <p>**Kvantitet på orderrad: 500 EA**</p><p>**Två laster: första last 200 EA, andra last 300 EA**</p><ol><li>Registrera inleverans i mobilappen för distributionslagerhantering för den första lasten för 100 EA<p>Sampling av kvalitetsartikel för 5 EA</p><p>Kvalitetsorder 1 för 5 EA</p><p>Arbete med inköpsorder på 95 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för den första lasten för 100 EA<p>Sampling av kvalitetsartikel för 5 EA</p><p>Kvalitetsorder 1 för 5 EA</p><p>Arbete med inköpsorder på 95 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för den andra lasten för 300 EA<p>Sampling av kvalitetsartikel för 15 EA</p><p>Kvalitetsorder 1 för 15 EA</p><p>Arbete med inköpsorder på 285 EA (artikelinförsel)</p></li></ol> |
| Ordning | Procent = 10 | Ja | <p>Plats: ja</p><p>ID-nummer: ja</p> | Nej | Inte aktuellt | <p>**Kvantitet på orderrad: 100**</p><ol><li>Registrera inleverans i mobilappen för distributionslagerhantering för 50 EA, LP1<p>Sampling av kvalitetsartikel för 5 EA</p><p>Kvalitetsorder 1 för 5 EA</p><p>Arbete med inköpsorder på 45 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för 50 EA, LP2<p>Sampling av kvalitetsartikel för 5 EA</p><p>Kvalitetsorder 1 för 5 EA</p><p>Arbete med inköpsorder på 45 (artikelinförsel)</p></li></ol> |
| Lasta | Fullständig registreringsskylt | Ja _(låst/inte redigerbart)_ | <p>Plats: ja</p><p>ID-nummer: Ja _(låst/inte redigerbart)_</p> | Nej | 3 | <p>**Två artiklar:**</p><ul><li>**Orderradens kvantitet för artikel A: 120 EA (4 lastpallar)**</li><li>**Orderradens kvantitet för artikel B: 90 EA (3 lastpallar)**</li></ul><p>**En last, två beläggningsrader med varje orderrad**</p><ol><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel A, 30 EA, LP1<p>Sampling av kvalitetsartikel för 30 EA</p><p>Kvalitetsorder 1 för 30 EA</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel A, 30 EA, LP2<p>Arbete med inköpsorder på 30 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel A, 30 EA, LP3<p>Arbete med inköpsorder på 30 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel A, 30 EA, LP4<p>Sampling av kvalitetsartikel för 30 EA</p><p>Kvalitetsorder 1 för 30 EA</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel B, 30 EA, LP5<p>Arbete med inköpsorder på 30 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel B, 30 EA, LP6<p>Arbete med inköpsorder på 30 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel A, 30 EA, LP7<p>Sampling av kvalitetsartikel för 30 EA</p><p>Kvalitetsorder 1 för 30 EA</p></li></ol> |
| Lasta | Fullständig registreringsskylt | Ja _(låst/inte redigerbart)_ | <p>Plats: ja</p><p>ID-nummer: Ja _(låst/inte redigerbart)_</p> | Ja | 3 | <p>**Två artiklar:**</p><ul><li>**Orderradens kvantitet för artikel A: 120 EA (4 lastpallar)**</li><li>**Orderradens kvantitet för artikel B: 90 EA (3 lastpallar)**</li></ul><p>**En last, två beläggningsrader med varje orderrad**</p><ol><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel A, 30 EA, LP1<p>Sampling av kvalitetsartikel för 30 EA</p><p>Kvalitetsorder 1 för 30 EA</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel A, 30 EA, LP2<p>Arbete med inköpsorder på 30 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel A, 30 EA, LP3<p>Arbete med inköpsorder på 30 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel A, 30 EA, LP4<p>Sampling av kvalitetsartikel för 30 EA</p><p>Kvalitetsorder 1 för 30 EA</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel B, 30 EA, LP5<p>Sampling av kvalitetsartikel för 30 EA</p><p>Kvalitetsorder 1 för 30 EA</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel B, 30 EA, LP6<p>Arbete med inköpsorder på 30 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för artikel A, 30 EA, LP7<p>Arbete med inköpsorder på 30 EA (artikelinförsel)</p></li></ol> |
| Lasta | Procent = 10 | Ja _(låst/inte redigerbart)_ | <p>Plats: nej</p><p>ID-nummer: nej</p> | Nej | Inte tillämpligt | <p>**Kvantitet på orderrad: 100 EA**</p><p>**Inga laster skapas. Orderomfång används.**</p><ol><li>Registrera inleverans i mobilappen för distributionslagerhantering för 50 EA, LP1<p>Sampling av kvalitetsartikel för 5 EA</p><p>Kvalitetsorder 1 för 5 EA</p><p>Arbete med inköpsorder på 45 EA (artikelinförsel)</p></li><li>Registrera inleverans i mobilappen för distributionslagerhantering för 50 EA, LP2<p>Sampling av kvalitetsartikel för 5 EA</p><p>Kvalitetsorder 1 för 5 EA</p><p>Arbete med inköpsorder på 45 EA (artikelinförsel)</p></li></ol> |

När en arbetare validerar en av de kvalitetsorder som visas i föregående register, genererar systemet automatiskt kvalitetsorderarbete för att flytta lager från kvalitetskontrollplatsen till den plats som har definierats i platsdirektivet för arbetsorder typen för _kvalitetsorder_. Du kan ställa in valfri plats för det här syftet, t.ex. en retur- eller en lagringsplats, beroende på testresultatet för kvalitetsordern. Ett exempel på den här inställningen finns i [exempelscenario](#example-scenario) i slutet av det här avsnittet.

Du kan öppna en kvalitetsorder som redan har validerats på nytt, förutsatt att kvalitetsordern som är relaterad till flyttningen av lagret från kvalitetskontrollplatsen inte har värde för **arbetsstatus** på *stängd* eller *pågår*.

## <a name="process-insights-when-multiple-quality-associations-coexist"></a>Bearbeta insikter när flera kvalitetsassociationer existerar

Mer än en kvalitetsassociation kan definieras för och tillämpas på samma källdokumentrad och fältet **Tillämplig lagerställetyp** kan anges till _Endast kvalitetshantering för lagerprocesser_ för vissa av dessa kvalitetsassociationer och _Alla_ för andra.

I följande exempel är värdet för **referenstypen** _inköp_.

1. Den första kvalitetsassociationen ställs in på följande sätt:

    - **Tillämplig lagerställetyp:** *Endast kvalitetshantering för lagerprocesser*
    - **Artikelkod:** *A0001*
    - **Kontokod:** *Alla*
    - **Testgrupp:** *bilaga*
    - **Artikelsampling:** *5 st*

1. Den andra kvalitetsassociationen ställs in på följande sätt:

    - **Tillämplig lagerställetyp:** *Alla*
    - **Artikelkod:** *Alla*
    - **Kontokod:** *Alla*
    - **Testgrupp:** *bilaga*
    - **Artikelsampling:** *1 st*

1. Den tredje kvalitetsassociationen ställs in på följande sätt:

    - **Tillämplig lagerställetyp:** *Endast kvalitetshantering för lagerprocesser*
    - **Artikelkod:** *Alla*
    - **Kontokod:** *104*
    - **Testgrupp:** *Impedans*
    - **Artikelsampling:** *Varannan registreringsskylt* (den här inställningen innebär att registreringsskylt som tas emot i första, tredje, femte och så vidare skapas en kvalitetsorder.)

1. Den fjärde kvalitetsassociationen ställs in på följande sätt:

    - **Tillämplig lagerställetyp:** *Alla*
    - **Artikelkod:** *Alla*
    - **Kontokod:** *Alla*
    - **Testgrupp:** *Impedans*
    - **Artikelsampling:** *5 st*

1. Den femte kvalitetsassociationen ställs in på följande sätt:

    - **Tillämplig lagerställetyp:** *Alla*
    - **Artikelkod:** *Alla*
    - **Kontokod:** *Alla*
    - **Testgrupp:** *kon*
    - **Artikelsampling:** *10 %*

En inköpsorder för kvantiteten 10 för artikel A0001 skapas nu för leverantör 104. Därefter registreras en inköpsorderrad som har kvantiteten 10 som mottagen på ett ID-nummer med hjälp av mobilappen för distributionslagerhantering. Detta är resultatet:

- Det finns en kvalitetsorder från den första kvalitetsassociationen för testgruppen *bilaga*. Kvantiteten är 5. Det finns ingen kvalitetsorder från den andra kvalitetsassociationen, eftersom kriterierna för den första kvalitetsassociationen är mer specifika i relation testgruppen *bilaga*.
- Det finns en kvalitetsorder för den tredje kvalitetsassociationen för testgruppen *Impedans*. Kvantiteten är 10. Det finns ingen kvalitetsorder från den fjärde kvalitetsassociationen, eftersom kriterierna för den första kvalitetsassociationen är mer specifika i relation testgruppen *Impedans*.
- Det finns en kvalitetsorder för den femte kvalitetsassociationen för testgruppen *kon*. Kvantiteten är 1.

I samband med att en kvalitetsorder skapas för var och en av de tre kvalitetsassociationerna skapas även kvalitetsartikelsampling. Den registrerade kvantiteten är endast 10. På grund av artikelns samplingsinställning är summan av de kvalitetsorderkvantitet som har skapats för *Endast kvalitetshantering för lagerprocesser* tillämpliga lagerställetyp 16, vilket överskrider den fysiska registrerade kvantiteten på 10. Därför skapas inte arbete för de totala kvalitetsorderkvantiteterna (16) eftersom bara 10 är fysiskt tillgängliga för transport till kvalitetskontrollplatsen. Den prioritet som används för att skapa kvalitetsartikelsampling följer ordningen för att skapa kvalitetsorder:

- **Första kvalitetsordern (kvantitet = 5):** Sampling av kvalitetsartikel skapas för 5. Kvantiteten 5 (10 – 5) behålls nu för att du senare ska kunna skapa sampling av kvalitetsartiklar.
- **Andra kvalitetsordern (kvantitet = 10):** Sampling av kvalitetsartikel skapas för 5. Kvantiteten0 (noll) behålls nu för att du senare ska kunna skapa sampling av kvalitetsartiklar.
- **Tredje kvalitetsordern (kvantitet = 1):** Ingen sampling av kvalitetsartikel skapas.

Som en del i processen med att skapa kvalitetsorder, skapas en lagerspärr av en kvantitet på 10. Den här lagerspärren refereras till mot var och en av de tre kvalitetsorder. Summan av antalet kvalitetsorder är 16.

När kvalitetsordern valideras försöker systemet skapa arbete med kvalitetsorder för varje kvalitetsorder som valideras. Eftersom summan av kvalitetsorderkvantiteter överskrider den kvantitet som verkligen har spärrats och därför är tillgänglig för att skapa arbetsuppgifter kan inte kvalitetsorderarbete skapas för de totala kvalitetsorderkvantitet som visas här. (Det här exemplet fortsätter det föregående exemplet)

1. **Validera den andra kvalitetsordern som skapas (kvantitet = 10). Kvalitetsorderarbete skapas för kvantiteten 4.**

    Skapandet av kvalitetsorderarbete utlöses av en ändring i kvantiteten för lagerspärr. Eftersom summan av kvantiteterna i kvalitetsordern är 16, kommer valideringen av 10 att medföra att de återstående kvalitetsorderkvantiteterna valideras som lika med 6. Kvantiteten för lagerspärren minskas från 10 till 6. Den reducerade kvantiteten av 4 har tilldelats för skapande av kvalitetsorderarbete.

2. **Validera den första kvalitetsordern som skapas (kvantitet = 5). Kvalitetsorderarbete skapas för kvantiteten 5.**

    Skapandet av kvalitetsorderarbete utlöses av en ändring i kvantiteten för lagerspärr. Eftersom summan av kvantiteterna i kvalitetsordern är 6, kommer valideringen av 5 att medföra att de återstående kvalitetsorderkvantiteterna valideras som lika med 1. Kvantiteten för lagerspärren minskas från 6 till 1. Den reducerade kvantiteten av 5 har tilldelats för skapande av kvalitetsorderarbete.

3. **Validera den tredje kvalitetsordern som skapas (kvantitet = 1). Kvalitetsorderarbete skapas för kvantiteten 1.**

    Skapandet av kvalitetsorderarbete utlöses av en ändring i kvantiteten för lagerspärr. Eftersom summan av kvantiteterna i kvalitetsordern är 1, kommer valideringen av 1 att medföra att de återstående kvalitetsorderkvantiteterna valideras som lika med 0 (noll). Lagerspärren tas bort (dvs. kvantiteten för lagerspärren minskas från 1 till 0). Den reducerade kvantiteten av 1 har tilldelats för skapande av kvalitetsorderarbete.

> [!NOTE]
> Genereringen av kvalitetsorderarbete beror på kvantiteten för lagerspärr som refereras mot en eller flera kvalitetsorder. Om summan av kvalitetsorderkvantiteterna överskrider den refererade kvantiteten för lagerspärr, bestämmer ordningen som kvalitetsorder valideras i skapandet av kvalitetsorderarbete.

## <a name="canceling-quality-item-sampling-work"></a>Avbryta sampling av kvalitetsartikel

Du kan avbryta arbetet som skapas för sampling av kvalitetsartikel. Om du vill kontrollera vad som händer när det här arbetet avbryts följer du stegen nedan.

1. Gå till **Warehouse management \> Inställningar \> Parametrar för Warehouse management**.
1. På fliken **allmänt** på snabbfliken **arbete** anger du alternativet **Avregistreringskvitto vid annullering av arbete** till ett av följande värden:

    - **Ja** – när sampling av kvalitetsartikel annulleras tas den associerade kvalitetsordern bort och lagret avregistreras.
    - **Nej** – när sampling av kvalitetsartikel annulleras tas den associerade kvalitetsordern inte bort och lagret avregistreras inte.

## <a name="cross-docking"></a>Direktleverans

Du kan skapa inställningar för kvalitetsassociations som skapar artikelsamplingsarbete. När direktutleverans däremot finns parallellt med en kvalitetsassociation som skapar sampling av kvalitetsartiklar, om det bara finns tillräckligt mycket kvantitet för att tillfredsställa direktutleverans, skapas bara artikelsamplingsarbete. I fall där alternativet **Aktivera kvalitetsorder för lagerprocesser** anges till _Ja_ för det mottagande lagerhuset och fältet **Tillämplig lagerställetyp** anges till _Endast kvalitetshantering för lagerprocesser_ för en kvalitetsassociation har skapandet av sampling av kvalitetsartiklar företräde framför skapandet av direktutleverans. Om kvantiteten överskrider kravet för direktutleverans skapas endast artikelsampling i systemet.

## <a name="destructive-testing"></a>Destruktivt test

Du kan definiera en testgrupp som utför destruktiv testning. När det gäller ett destruktivt test är antagandet att den kvantitet av artikeln som testas kommer att förstöras under testet, oavsett testresultatet. Sättet som funktionen _Kvalitetshantering för lagerprocesser_ stöder destruktiv testning liknar det sätt som kvalitetshantering stöder det när funktionen inte är på. Innan kvalitetsordern kan valideras, måste kvalitetskontrollanten ange plockplatsen för den kvantitet som har förstörts. Du kan registrera plockning från sidan kvalitetsorder genom att välja **Lager \> Plockning** i åtgärdsfönstret. När plockningen för kvantiteten för kvalitetsorder har registrerats kan valideringen slutföras.

## <a name="example-scenario"></a>Exempelscenario

### <a name="prepare-the-scenario"></a>Förbered scenariot

För att kunna arbeta i det här scenariot måste du förbereda systemet på följande sätt:

- Kontrollera att demodata är installerade i systemet och välj den juridiska personen **USMF**.
- Aktivera funktionen _Kvalitetshantering för lagerprocesser_ i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Konfigurera lagerställe 51 om du vill använda funktionen _Kvalitetshantering för lagerprocesser_ genom att följa dessa steg:

    1. Gå till **Warehouse management \> Inställningar \> Lagerställe \> Lagerställen**.
    1. Välj lagerställe 51.
    1. På snabbfliken **lagerställe**, ange alternativet **aktivera kvalitetsorder för lagerprocesser** till *Ja*.

### <a name="quality-in-setup--move-to-the-quality-control-location"></a>Kvalitetsinställningar – flytta till kvalitetskontrollplatsen

Nu måste du förbereda en grundinställning som gör det möjligt för ditt system att stödja funktionen _Kvalitetshantering för lagerprocesser_ för lagerställe 51. (Demonstrationsdata definierar en kvalitetshanteringsplats med namnet *QMS*. Den platsen refereras flera gånger i det här scenariot.) Du förbereder följande element, enligt beskrivningen i avsnittet nedan:

- Arbetsklass
- Arbetsmall
- Platsdirektiv
- Artikelsampling
- Kvalitetsassociation
- Menyalternativ på mobil enhet

#### <a name="work-class-for-quality-in"></a>Arbetsklass för kvalitet in

1. Gå till **Warehouse management \> Inställningar \> Arbete \> Arbetsklasser**.
1. Skapa en arbetsklass och ange följande värden:

    - **Arbetsklass-ID:** _QualityIn_
    - **Beskrivning:** _sampling av kvalitetsartikel_
    - **Arbetsordertyp:** _sampling av kvalitetsartikel_

#### <a name="work-template"></a>Arbetsmall

1. Gå till **Warehouse management \> Inställningar \> Arbete \> Arbetsmallar**.
1. Ange fältet **Typ av arbetsorder** till _sampling av kvalitetsartikel_.
1. Skapa en arbetsmall och ange följande värden:

    - **Arbetsmall**_: 51 kvalitet_
    - **Arbetsmallbeskrivning:** _51 kvalitet_

1. Lägg till en rad till arbetsmallen och ange följande värden:

    - **Arbetstyp:** _plockning_
    - **Arbetsklass-ID:** _QualityIn_

1. Lägg till en andra rad till arbetsmallen och ange följande värden:

    - **Arbetstyp:** _Placera_
    - **Arbetsklass-ID:** _QualityIn_

#### <a name="location-directive"></a>Platsdirektiv

1. Gå till **Warehouse management \> Inställningar \> Platsdirektiv**.
1. Ange fältet **Typ av arbetsorder** till _sampling av kvalitetsartikel_.
1. Skapa ett platsdirektiv. och ange följande värden:

    - **Namn:** _51 till kvalitet_
    - **Arbetstyp:** _Placera_
    - **Plats:** 5
    - **Lagerställe:** _51_

1. Lägg till en rad för platsdirektivet och ange följande värden:

    - **Från kvantitet:** _1_
    - **Till kvantitet:** _1000000_

1. Skapa en åtgärd för platsdirektiv och ange följande värde:

    - **Namn:** _kvalitet_

1. Välj den för den nya platsdirektivåtgärden **Redigera fråga** och ange en post för **intervall** som har följande värden:

    - **Register:** *platser*
    - **Fält:** _platsprofil-ID_
    - **Kriterier:** *QMS*

1. Välj **OK** för att spara frågan och det nya platsdirektivet.

Sedan måste du ändra ordningsföljden för de befintliga direktiven för inköpsorderplats för lagerställe 51. Demonstrationsdata innehåller två platsdirektiv som har ett värde på **arbetsordertyp** på _inköp_: ett som kallas _51 QMS_ och den andra heter _51 PO direkt_. För att säkerställa att funktionen *Kvalitetshantering för lagerprocesser* används för lagerställe 51, måste du se till att platsdirektivet _51 QMS_ inte används. I stället för att ta bort det platsdirektivet (eftersom du kanske vill använda det i framtiden) kan du dock bara ändra ordningen.

1. Gå till **Warehouse management \> Inställningar \> Platsdirektiv**.
1. Ange **Inköpsorder** i fältet till _Inköpsorder_.
1. I sekvenslistan väljer du ordningsnummer 5 för platsdirektivet _51 PO direkt_.
1. Flytta vald sekvens upp till löpnummer 4.
1. Kontrollera att löpnumret _51 QMS_ platsdirektivet är nu minst 5.

#### <a name="item-sampling"></a>Artikelsampling

Funktionen _Kvalitetshantering för lagerprocesser_ lägger till några nya funktioner för artikelsampling. Värdet **Samplingsområde** kan nu vara _Order_, _Leverans_ eller _Last_ och värdet **Samplingskvantitet** kan du nu vara _Full registreringsskylt_.

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Artikelsampling**.
1. Skapa en artikelsamplingspost och ange följande värden:

    - **Artikelsampling:** _3:e LP_
    - **Beskrivning:** _var tredje registreringsskylt_
    - **Samplingsområde:** _Order_

1. Ange snabbfliken **Samplingskvantitet**, ange fältet **Kvantitetsspecifikation** till _Full registreringsskylt_.
1. På snabbfliken **Process**, ange fältet **Per N:te registreringsskylt** till _3_.
1. I avsnittet **Per lagringsdimension** aktivera både **lagerställe** och **lagerstatus**.

#### <a name="quality-associations"></a>Kvalitetsassociationer

Skapa en kvalitetsassociation som ska använda den nya artikelsamplingen.

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Kvalitetsassociationer**.
1. Skapa en kvalitetsassociationspost och ange följande värden:

    - **Referenstyptype:** _inköp_
    - **Artikelkod:** _tabell_
    - **Artikel:** _M9201_
    - **Plats:** _5_

1. På snabbfliken **Process**, ange fältet **händelsetyp** till *registrering*.
1. På snabbfliken **villkor** anger du fältet **Tillämplig lagerställetyp** till *Kvalitetshantering för lagerprocesser*.
1. På snabbfliken **Kvalitetsorderprocess** ange fältet **Policy för kvalitetsbearbetning** till _skapa kvalitetsorder_.
1. På snabbfliken **specifikationer** högerklickar du i fältet **Testgrupp** och väljer **Visa information** för att öppna sidan **Testgrupper**.
1. På fliken **Testgruppen** på fliken **Översikt** i det övre rutnätet, skapa en testgrupp och ange följande värden:

    - **Testgrupp:** _QMS_
    - **Beskrivning:** _QMS test_
    - **Godtagbar kvantitet:** _100_
    - **Artikelsampling:** _3:e LP_ (välj)

1. På fliken **översikt** i det nedre rutnätet lägger du till en post för ett test och anger följande värden:

    - **Sekvens:** *1*
    - **Test:** *mätning av bilaga*

1. På fliken **Test** i det nedre rutnätet, ange följande värden:

    - **Testvariabler:** *Godkänd/underkänd*
    - **Standardresultat:** *Godkänd*

1. Spara den nya testgruppen och stäng sidan **testgrupper**.
1. Gå tillbaka till sidan **Kvalitetsassociationer** i fältet **Testgrupp** välj **QMS**.
1. Spara posten.

#### <a name="mobile-device-menu-items-for-quality-in"></a>Menyartiklar för mobila enheter för kvalitet in

Om du vill slutföra inställningarna för att flytta varor till platsen för kvalitetskontroll måste du göra samplingen av kvalitetsartikel tillgänglig från et menyalternativ på en mobil enhet.

1. Gå till **Warehouse management \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Välj menyalternativet för mobil enhet **inköpsartikelinförsel**.
1. På snabbfliken **arbetsgrupper** lägger du till arbetsklass-ID *QualityIn*.

#### <a name="summary-your-setup-to-move-goods-to-quality-control"></a>Sammanfattning: din inställning för att flytta varor till kvalitetskontroll

Du har nu definierat en kvalitetsassociation som använder funktionen *kvalitetshantering för lagerprocesser* för att utlösa skapandet av en kvalitetsorder. Du har ställt in uppgifterna om arbete och platsdata för lagerställe 51, för att säkerställa att specifikt arbete skapas när inköpsregistrering görs för artikel M9201. Den här inställningen garanterar att alla tredje registreringsskyltar som registreras flyttas till en kvalitetsplats (_QMS_) och att en kvalitetsorder skapas för kvantiteten för registreringsskylten. Allt annat flyttas till artikelinförsel istället för kvalitetskontrollplatsen.

### <a name="process-quality-management-work"></a>Behandla kvalitetshanteringsarbete

1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Skapa en inköpsorder och ange följande värden:

    - **Ange leverantörskonto:** *104*
    - **Lagerställe:** *51*

1. Lägg till en inköpsorderrad och ange följande värden:

    - **Artikel:** *M9201*
    - **Kvantitet:** *20*
    - **UoM:** *ea*
    - **Lagerställe:** *51*

1. Skriv ned inköpsordernumret så att du kan använda det senare.
1. Gå till en mobil enhet eller emulator som kör mobilappen för distributionslagerhantering och logga in i distributionslager 51 med hjälp av *51* som användar-ID och *1* som lösenord.
1. Gå till **ingående \> inleverans av inköp** och ange följande värden:

    - **PONum:** Numret på inköpsorderraden du just skapade
    - **Kvantitet:** *5*
    - **Enhet:** *ea*

1. Fortsätt att ta emot mot raden, *5 ea* i taget tills raden har tagits emot helt. (Totalt fyra registreringsskyltar kommer att skapas.)
1. Logga ut från mobilappen Hantering av distributionslager.
1. Tillbaka till webbklienten, gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Sök upp och öppna din inköpsorder.
1. I avsnittet **inköpsorderrader** välj rad för artikelnummer *M9201* och välj sedan **inköpsorderrader \> arbetsuppgifter**.
1. Observera att det andra och tredje arbetsrubriken som skapas är vanligt artikelinförselarbete, medan de första och fjärde arbetsrubrikerna är en kvalitetsartikel som samplingsarbete. Resultatet är förenligt med inställningen av artikelsampling, som är konfigurerad för att sampla var tredje registreringsskylt.

#### <a name="move-to-the-quality-control-location"></a>Flytta till kvalitetskontrollplatsen

Du kommer nu att flytta registreringsskyltarna till de angivna platserna. Den första och fjärde registreringsskylten kommer att gå till kvalitetskontrollplatsen, medan den andra och den tredje registreringsskylt går direkt till lagringen.

1. Gå till en mobil enhet eller emulator som kör mobilappen för distributionslagerhantering och logga in i distributionslager 51 med hjälp av *51* som användar-ID och *1* som lösenord.
1. Gå till **ingående \> inköpsartikelinförsel** och inför varje registreringsskylt från föregående procedur tills du har stängt allt arbete.

#### <a name="summary-process-quality-management-work"></a>Sammanfattning: Behandla kvalitetshanteringsarbete

Nu använder du samplingsarbetet för kvalitetsartiklar för de första och fjärde registreringsskyltarna genom att flytta dem till kvalitetskontrollplatsen. Du har också lägga undan den andra och den tredje registreringsskylten. Nästa steg är att göra kvalitetsordertestning och -kontroll.

### <a name="quality-out-setup-move-from-the-quality-control-location-to-storage-or-return"></a>Inställning av kvalitet: flytta från kvalitetskontrollplatsen till lagring eller retur

När medarbetarna rapporterar resultat för kvalitetsorder skapas arbetet automatiskt i systemet.

Du kommer nu att fortsätta med den grundläggande inställningen av arbetsklassen, arbetsmallen och platsdirektivet för att aktivera kvalitetshantering för lagerprocesser så att det nödvändiga arbetet kan skapas för att flytta kvantiteten för kvalitetsordern från kvalitetskontrollplatsen till ett bestämt lagerställe.

#### <a name="work-class-for-quality-out"></a>Arbetsklass för kvalitet ut

1. Gå till **Warehouse management \> Inställningar \> Arbete \> Arbetsklasser**.
1. Skapa en arbetsklass och ange följande värden:

    - **Arbetsklass-ID:** *QualityOut*
    - **Beskrivning:** *kvalitet ut*
    - **Arbetsordertyp:** *kvalitetsorder*

#### <a name="work-templates"></a>Arbetsmallar

1. Gå till **Warehouse management \> Inställningar \> Arbete \> Arbetsmallar**.
1. Ändra värdet **Arbetsordertyp** till *kvalitetsorder*.
1. Skapa en arbetsmall och ange följande värden:

    - **Arbetsmall:** *51 kvalitet ut*
    - **Arbetsmallbeskrivning:** *51 kvalitet ut*

1. Lägg till en rad och ange följande värden.

    - **Arbetstyp:** *plockning*
    - **Arbetsklass-ID:** **QualityOut**

1. Lägg till en andra rad och ange följande värden.

    - **Arbetstyp:** *Placera*
    - **Arbetsklass-ID:** *QualityOut*

#### <a name="location-directives"></a>Platsdirektiv

1. Gå till **Warehouse management \> Inställningar \> Platsdirektiv**.
1. Ändra värdet **Arbetsordertyp** till *kvalitetsorder*.
1. Skapa ett platsdirektiv. och ange följande värden:

    - **Namn:** *51 skickas*
    - **Arbetstyp:** *Placera*
    - **Plats:** *5*
    - **Lagerställe:** *51*

1. I åtgärdsfönstret, välj **Redigera fråga** för att öppna dialogrutan för redigering.
1. Ange följande värden på fliken **Sortiment**:

    - **Register:** *kvalitetsorder*
    - **Fält:** *Status*
    - **Kriterier:** *skicka*

1. Välj **OK** om du vill spara frågan och stänga dialogrutan.
1. På snabbfliken **Rader** lägg till en rad och ange följande värden:

    - **Från kvantitet:** *1*
    - **Till kvantitet:** *1000000*

1. På snabbfliken **platsdirektivåtgärder** lägger du till en rad och anger följande värde:

    - **Namn:** *skickas*

1. På snabbfliken **platsdirektivåtgärder**, välj **Redigera fråga** för att öppna dialogrutan för redigering.
1. Ange följande värden på fliken **Sortiment**:

    - **Register:** *platser*
    - **Fält:** *zon-ID*
    - **Kriterier:** *bulk*

1. Välj **OK** om du vill spara frågan och stänga dialogrutan.
1. I åtgärdsfönstret, välj **Spara** och spara det nya platsdirektivet.
1. Skapa ett andra platsdirektiv. och ange följande värden:

    - **Namn:** *51 misslyckades*
    - **Arbetstyp:** *Placera*
    - **Plats:** *5*
    - **Lagerställe:** *51*

1. I åtgärdsfönstret, välj **Redigera fråga** för att öppna dialogrutan för redigering.
1. Ange följande värden på fliken **Sortiment**:

    - **Register:** *kvalitetsorder*
    - **Fält:** *Status*
    - **Kriterier:** *misslyckades*

1. Välj **OK** om du vill spara frågan och stänga dialogrutan.
1. På snabbfliken **Rader** lägg till en rad och ange följande värden:

    - **Från kvantitet:** *1*
    - **Till kvantitet:** *1000000*

1. På snabbfliken **platsdirektivåtgärder** lägger du till en rad och anger följande värde:

    - **Namn:** *misslyckades*

1. På snabbfliken **platsdirektivåtgärder**, välj **Redigera fråga** för att öppna dialogrutan för redigering.
1. Ange följande värden på fliken **Sortiment**:

    - **Register:** *platser*
    - **Fält:** *zon-ID*
    - **Kriterier:** *återgå*

1. Välj **OK** om du vill spara frågan och stänga dialogrutan.
1. I åtgärdsfönstret, välj **Spara** och spara det nya platsdirektivet.

#### <a name="mobile-device-menu-items-for-quality-out"></a>Menyartiklar för mobila enheter för kvalitet ut

1. Gå till **Warehouse management \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Välj menyalternativet för mobil enhet **QMS artikelinförsel**.
1. På snabbfliken **arbetsgrupper** lägger du till arbetsklass-ID *QualityPut*.

Lagerarbetare kan nu välja beställningsarbete med hjälp av menyartikeln **QMS artikelinförsel**. Varor som inte godkänts kvalitetskontrollvaror kan placeras på en returplats, och varor som skickas kan placeras på platsen bulk-001.

#### <a name="summary-your-setup-to-move-goods-from-quality-control"></a>Sammanfattning: din inställning för att flytta varor från kvalitetskontroll

Du har ställt in uppgifterna om arbete och platsdata för lagerställe 51, för att säkerställa att arbete skapas automatiskt när kvalitetsorder slutförs. Den här inställningen garanterar att varje kvalitetskontrollerad registreringsskylt flyttas till en bulkplats eller till en returplats.

### <a name="process-quality-management-work"></a>Behandla kvalitetshanteringsarbete

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Kvalitetsorder**.
1. Välj den första kvalitetsordern för de kvantiteter som har registrerats.
1. Välj **validera**. Statusen för testet uppdateras till *underkänd*.
1. Gå till **Warehouse management \> Allt arbete**.
1. Öppna det arbete som du just har skapat och observera att värdet **arbetsordertyp** är *kvalitetsorder*. Arbetet innehåller en rad där läggplatsen är *retur* och statusen är *underkänd*. (Om kvalitetsorderns status var *godkänd*, skulle läggplatsen vara *Bulk* i stället.)
1. Gå tillbaka till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Kvalitetsorder**.
1. Välj den andra kvalitetsordern för de artiklar som har registrerats.
1. Välj **resultat** ovanför det nedre rutnätet. Uppdatera värdet **Resultatkvantitet** till *5* och kontrollera att värdet **Testresultat** ändras till en bockmarkering.
1. Markera **Validera** och stäng sedan sidan.
1. Tillbaka till sidan **kvalitetsorder**, välj **validera** och gör valideringen. Checkens status uppdateras till *Godkänd*.

    > [!NOTE]
    > Vid valideringshändelsen utlöser skapande av kvalitetsordern för att kvantiteten ska flyttas från kvalitetskontrollplatsen till en ny plats.

1. Gå till **Warehouse management \> Allt arbete**.
1. Välj det arbete som just har skapats och observera att en andra rubrik för kvalitetsorderarbete har skapats, där läggplatsen är *BULK-001*.
1. Gå till en mobil enhet eller emulator som kör mobilappen för distributionslagerhantering och logga in i distributionslager 51 med hjälp av *51* som användar-ID och *1* som lösenord.
1. Gå till **kvalitet \> Inlagra från QMS** och behandla var och en av de två registreringsskyltarna som hör till båda arbetsdelarna så att allt arbete stängs.

> [!NOTE]
> Överväg att lägga till posten kvalitet ut på en menyartikel på en mobil enhet där aktivitetskoden är *Visa öppna arbetslista*. Ett exempel finns i menyalternativet på mobila enheten som heter **arbetslista** i demonstrationsdata. Lägg först till arbetsklassen *kvalitetsorder* på ett menyalternativ som användaren anger, eftersom denna arbetsklass krävs för att arbete ska visas i arbetslistan. Lägg sedan till arbetsklassen *Kvalitetsorder* till menyalternativet **arbetslista**. Användare som har tillgång till arbetslistan kan då välja och bearbeta det arbete som skapas automatiskt av valideringen av kvalitetsorder.

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvalitets- och avvikelsehantering – en översikt](quality-management-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]