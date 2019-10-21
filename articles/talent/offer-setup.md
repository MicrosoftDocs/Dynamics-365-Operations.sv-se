---
title: Ställ in erbjudandehantering
description: I det här avsnittet beskrivs hur du ställer in erbjudanden i Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 706766ba5133af03d00df99dba1c2a7b0405cd86
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010854"
---
# <a name="set-up-offer-management"></a>Ställ in erbjudandehantering 

[!include [banner](includes/banner.md)]

När en kandidat flyttas till erbjudandefasen i Dynamics 365 Talent: Attract måste du se till att erbjudandena snabbt kan skapas för kandidater, godkännas efter behov och skickas ut till kandidaten. Eftersom de flesta erbjudanden är standard måste de skapas från återanvändningsbara mallar. I Attract samlas alla erbjudanden i ett erbjudandepaket som består av ett eller flera erbjudandedokument. 

Det här avsnittet beskriver de steg som en Attract-administratör skulle följa för att konfigurera olika erbjudandepaketmallar som en del av erbjudandehanteringen i Attract. Användare som inte har administratörsroll har inte åtkomst till dessa funktioner.

>[!NOTE]
> Erbjudandehanteringsfunktioner är tillgängliga som en del av tillägget för omfattande anställning.

## <a name="offer-data"></a>Erbjudandedata 

Erbjudandedata utgör den minsta enheten inne i erbjudandepaketmallen. Ett typiskt erbjudande består av standardtext och en uppsättning värden. Uppsättningar med värden är de enda enheter som kan ändras mellan erbjudanden. När du skapar erbjudandet är den viktigaste aspekten att den person som skapat erbjudandet kan fokusera på listan med platshållare för erbjudandedata som finns i erbjudandepaketmallen. Gör följande om du vill ställa in erbjudandedata.

1.  Gå till **Erbjudandehantering**.

1.  Expandera avsnittet **Bibliotek** under det vänstra navigeringsfönstret och gå sedan till **erbjudandedata**.

    >[!NOTE]
    > På sidan **erbjudandedata** finns avsnitten **kandidatdetaljer** och **jobbdetaljer**. Attract ger några platshållare för erbjudandedata från början.
    
    > Det finns avsnitt på sidan för att ordna olika platshållare för erbjudandedata i logiska grupper. Dessa avsnitt kan hjälpa dig med underhåll av erbjudandedata och ifyllning av data under processen för skapande av erbjudandet.

1.  För att skapa ett nytt erbjudandedataavsnitt, klicka på **Lägg till ett avsnitt** och ange ett unikt namn för avsnittet.

1.  Lägg till platshållare för erbjudandedata till ett visst avsnitt genom att klicka på **Lägg till erbjudandedata** och ange ett unikt namn för platshållaren.

1.  Hovra över avsnittsnamnet om du vill redigera namnet på ett avsnitt och uppdatera namnet.

1.  Om du vill redigera namnet på befintliga platshållare för erbjudandedata, se till att platshållaren inte är en del av en mall. För sedan muspekaren över namnet på platshållaren för erbjudandedata och uppdatera namnet om det behövs.

1. Om du vill radera namnet på befintliga platshållare för erbjudandedata, se till att platshållaren inte är en del av en annan mall. För sedan muspekaren över platshållaren och när ikonen för papperskorgen visas klickar du på papperskorgen för att ta bort platshållaren för erbjudandedata.
    >[!NOTE]
    > Du kan se hur många mallar som en platshållare för erbjudandedata tillhör genom nummerindikatorn bredvid varje erbjudandedata. 

1. Ta bort ett avsnitt genom att hovra över namnet. Om ingen av platshållarna för erbjudandedata inuti avsnittet visas i en mall klickar du på ikonen för papperskorgen om du vill ta bort den. 
    >[!NOTE]
    > Om du tar bort avsnittet, tas även alla platshållarna för erbjudandedata bort inne i avsnittet.

När platshållarna för erbjudandedata har skapats kan du använda dem över alla dokumentmallar. Platshållare för erbjudandedata är inte begränsade till en specifik mall – samma uppsättning kan användas på alla mallar.

## <a name="offer-data-rules"></a>Regler för erbjudandedata

De flesta företag har regler för hur erbjudande måste skapas. En organisation kan exempelvis kräva att erbjudandet för maximal årslön för en viss kombination av plats och tjänsteåldernivå måste vara inom ett visst intervall eller att det inte finns några specifika värden för erbjudandenivån för den nya anställningen. Attract ger stöder för närvarande alla dessa dataregler genom att använda en CSV-fil.

Gör följande om du vill förbereda CSV-filen med dataregler.

1.  Bestäm platshållaren för erbjudandedata för regeluppsättningen. Till exempel **årslön**.

1.  Identifiera det beroende platshållarvärdet för erbjudandedata. Till exempel **Plats för jobbet** och **Nivå**.

1.  Ange kolumner 1 och 2 som **Plats för jobbet** och **Nivå**.

1.  Gör kolumnerna 3 och 4 till **Årslön** om du vill överföra ett intervallvärde. Gör endast kolumn 3 **Årslön** om du vill överföra ett specifikt värde istället för ett intervall.

1.  Fyll i Microsoft Excel-filen utifrån dina obligatoriska roller.

1.  Kontrollera att varje rad är en unik kombination av de värden som sammanfogas.

1.  Spara filen som ett CSV-format.

Gör följande om du vill överföra filen med regler för erbjudandedata.

1.  Gå till **Erbjudandehantering**.

1.  Expandera avsnittet **Bibliotek** under det vänstra navigeringspanelen och gå sedan till **Regler för erbjudandedata**.

1.  Klicka på **Ny datauppsättning** för att visa dialogrutan **överför**.

1.  Ange ett unikt namn för regeluppsättningen och överför sedan den sparade CSV-filen.

1.  Klicka på **Lägg till**.
    Regeluppsättningen ska bearbetas i bakgrunden och du får ett meddelande i appen och via e-post så snart den är slutförd.

    Du meddelas om fel uppstår under bearbetningen av överföringen. Du kan sedan hämta felloggen, korrigera filen och överföra den igen.

1.  Använd ellips-knappen (**...**) om du vill hämta regeluppsättningen och uppdatera uppsättningen med värden. När du har uppdaterat, kan du överföra filen igen.

1.  Du kan ta bort en befintlig överföring av regeluppsättning om platshållaren som definieras inte används i en annan dokumentmall.

>[!NOTE]
> - Varje platshållare kan bara ha en unik uppsättning kolumner som den är beroende av. Om till exempel **årslön** är beroende av **plats för jobbet** och **nivå** kan du inte överföra en annan regeluppsättning där **årslön** är beroende av en annan uppsättning kolumner.

> - Du kan hämta exempel på regeluppsättningar för erbjudandedata på fliken **Exempel** på sidan **Regler för erbjudandedata**.

> - När en person som skapat erbjudandet åsidosätter de värden som rekommenderas av regler för erbjudandedata markeras erbjudandet som icke-standardiserat och arbetsflödet för godkännande av erbjudandet kommer att vara bestämt.

## <a name="document-templates"></a>Dokumentmallar

En erbjudandedokumentmall kan hjälpa administratörer att skapa erbjudandebrev. Erbjudandedokumentmallen är en kombination av text som ska ingå i erbjudandet samt definierade platshållare för erbjudandedata. 

Gör följande om du vill skapa en erbjudandedokumentmall.

1.  Gå till **Erbjudandehantering**.

1.  Expandera avsnittet **Bibliotek** under det vänstra navigeringsfönstret och gå till **Mallar**.

    Sidan **mallar** visar en lista över dokumentmallar som redan har definierats.

1.  Klicka på **Ny mall** om du vill skapa en ny dokumentmall.

1.  Ange ett unikt namn för mallen och klicka på **Skapa**.

1.  Använd RTF-redigeraren för att sätta in och redigera innehållet i erbjudandedokumentet. Du kan infoga tabeller, bilder och hyperlänkar med hjälp av alternativen längst upp i textredigeraren.

1.  Du kan infoga platshållare för erbjudandedata i malldokumenten för erbjudandet genom att:

    - Dra och släpp från den högra rutan.

    - Hashtag platshållaren för erbjudandedata direkt till en position. Skriva **\#** och sedan börja skriva in namnet på platshållaren för erbjudandedata. Alternativen visas i den nedrullningsbara listan. Klicka eller tryck på **ange** för att infoga platshållaren för erbjudandedata.

    >[!NOTE]
    > - Hovra över platshållaren för erbjudandedata om du vill associera en platshållare till dokumentmallen för erbjudandet utan att visa dess värde för kandidaten och klicka på **fäst**-ikonen. Detta för platshållaren till avsnittet **Fästa erbjudandedata** av dokumentmallen för erbjudandet. Ta bort genom att följa samma steg men klicka på **ta bort** i listan över platshållare för erbjudandedata.

    > - Om du vill visa listan över aktiva platshållare för erbjudandedata, växla till fliken **aktiva** i det högra fönstret.

    > - Om du infogar en platshållare som drivs av en regeluppsättning för erbjudandedata visas beroendet för den platshållaren för erbjudandedata på andra värden.

    > - Alternativt kan du **Importera** innehåll från en .docx-fil på den lokala datorn och redigera efter behov. På så sätt måste du inte skriva in allt innehåll i redigeraren.

1. Om du vill förhandsgranska erbjudandedokumentet, använd alternativet **förhandsgranskning** överst på sidan.

1. För att kontrollera om en person som skapat erbjudandet kan redigera erbjudandedokumentets innehåll, använd alternativet **hantera behörighet** överst på sidan. Om du vill att personen som skapade erbjudandet endast ska infoga platshållarvärden och inte redigera text, anger du behörighetsvärdet till **Nej**.

1. Spara framstegen genom att klicka på **Spara**. Mallen sparas i utkastform.

1. För att avsluta och markera dokumentet som publicerat klickar du på **Slutför**.

1. Du kan se vilka dokumentmallar som för närvarande är aktiva, i utkastläget, och som har arkiverats och inte längre används av upplevelsen för biblioteket för dokumentmallar.

>[!NOTE]
> Du kan ta bort alla erbjudandedokumentmallar som inte är en del av en befintlig erbjudandepaketmall.


## <a name="offer-package-templates"></a>Erbjudandepaketmallar

Erbjudandet är erbjudandet artefakterna som delas med sökande och består av en kombination av en eller flera erbjudandet dokumentmallar. Gör följande om du vill skapa ett erbjudandepaket.

1.  Gå till **Erbjudandehantering**.

1.  Gå till **paket** från det vänstra navigeringsfönstret.

    En lista visas över aktiva paketmallar som är tillgängliga för skapare av erbjudanden som ska användas.

1.  För att skapa ett nytt erbjudandepaket klickar du på **Nytt paket**.

1.  Ange ett unikt namn och klicka på **Skapa**.

1.  Klicka på **Lägg till mall**.

    >[!NOTE]
    > - Du kan välja att skapa en ny mall eller välja från en befintlig.

    > - Om du vill lägga till en befintlig mall måste du kontrollera att erbjudandedokumentmallen har sparats, slutförts och markerats som aktiv.
    
    > - Du kan välja så många dokumentmallar som du vill. 
    
1.  Klicka på **Klar** för att gå tillbaka till **pakethantering**.

    Du kan konfigurera dokumentens ordningsföljd och även markera om specifika erbjudandedokument krävs vid skapandet av erbjudandet. Den som skapar erbjudandet har ett alternativ för att ta bort dokument markerade som **Krävs inte**.

1. För att spara erbjudandepaketmallen så att den kan användas av alla skapare av erbjudanden, klicka på **spara och publicera**.

   För att visa utkast av erbjudandepaketmallar, gå till fliken **utkast**. Om en ändring görs i erbjudandetpaketmallen måste den sparas och publiceras igen.

## <a name="configure-an-offer-process"></a>Konfigurera en erbjudandeprocess

Det finns flera olika delar av erbjudandets skapandeprocess som kan konfigureras av en Attract-administratör.

- **Erbjudandegodkännanden** - Välj om erbjudandegodkännande krävs innan erbjudandet kan skickas till kandidaten. Som administratör kan du också bestämma om erbjudandegodkännanden sker i ordningsföljd eller parallellt med godkännandearbetsflödet. Du kan också bestämma om erbjudandets godkännare måste lägga till en kommentar tillsammans med deras erbjudandegodkännande. Erbjudandegodkännanden är obligatoriska för alla erbjudanden som inte är standard.

- **Kandidatens erfarenhet av erbjudandet** - som administratör kan du ange om alla erbjudanden har ett förfallodatum och i så fall vad standardförskjutningen för förfallodatum ska vara. Du kan också ange om kandidater kan avvisa ett erbjudande.

- **e-signaturer** - Som administratör kan du också välja metoden kandidater kan använda för att skriva under erbjudanden.
    - Adobe Sign - Alla erbjudandepaket skickas och signerats via Adobe Sign. Varje erbjudandeskapare publicerar erbjudandet måste ha Adobe Sign-kontot anslutet till Attract. Adobe Sign-licenser och en kostnadsfri utvärderingsversion finns i [länk](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).

    - DocuSign - Alla erbjudandepaket skickas och signerats via DocuSign. Varje erbjudandeskapare publicerar erbjudandet måste ha DocuSign-kontot anslutet till Attract. 
    
    - ESign - Detta är standardalternativet, tillhandahålles direkt vid leverans, där användaren kan registrera ett erbjudande genom att ange deras namn och initialer.


Mer information om processen att skapa erbjudanden finns i [skapa, godkänna och signera erbjudanden](./creating-offers.md).
