---
title: Komponenter för ekonomisk rapport
description: Den här artikeln innehåller en beskrivning av hur komponenter eller byggblock för rapportdefinitioner används vid ekonomisk rapportering. Dessa byggblock omfattar raddefinitioner, kolumndefinitioner och rapporteringsträddefinitioner. Artikeln innehåller en beskrivning av hur du ordnar och låser byggblock och hur du arbetar med byggblocksgrupper.
author: aprilolson
manager: AnnBe
ms.date: 10/27/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0829c9eb54a8a5ca1f78bfe85de4779e541b945a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553938"
---
# <a name="financial-report-components"></a>Komponenter för ekonomisk rapport

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller en beskrivning av hur komponenter eller byggblock för rapportdefinitioner används vid ekonomisk rapportering. Dessa byggblock omfattar raddefinitioner, kolumndefinitioner och rapporteringsträddefinitioner. Artikeln förklarar hur du ordnar och låser byggblock.

Designfilosofin bakom ekonomiska rapporteringsdesigner är att dela upp information i de minsta komponenterna eller byggblocken och sedan mixa och matcha komponenterna efter behov. Därför är formateringen separerad från dina ekonomiska data och du kan ändra en rapports design utan att ändra ekonomiska data i Microsoft Dynamics ERP-system. Med hjälp av den här byggblocksstrategin kan du kombinera text, belopp och beräkningar för att skapa de rapporter du behöver. Dessutom uppmuntrar den här flexibiliteten till kreativitet genom att göra det enklare för dig att visa dina operationer på olika sätt. De enskilda byggblocken i en rapportdefinition liknar ett tredimensionellt kalkylblad, men är mer effektiva. En rapportdefinitionen specificerar raddefinitionen, kolumndefinitionen och en valfri definition av det rapporteringsträd som ska användas för rapporten. Den innehåller också information om var du lagrar den genererade rapporten och hur du öppnar den.

## <a name="building-blocks-of-a-report"></a>Byggblock i en rapport

| Byggblock            | beskrivning | Mer information |
|---------------------------|-------------|----------------------|
| Raddefinition            | En raddefinition definierar de beskrivande raderna (till exempel löner eller försäljning) i en rapport. Den anger också de segmentvärden eller dimensioner som innehåller värdena för varje radartikel och innehåller även radformatering och beräkningar. | [Raddefinitioner](row-definitions-financial-reporting.md) |
| Kolumndefinition         | En kolumndefinition definierar perioden som ska användas när data hämtas från ekonomiska dimensioner. Den innehåller även kolumnformatering och beräkningar. | [Kolumndefinitioner](column-definitions-financial-reports.md) |
| Rapportträddefinition | En rapportträddefinition liknar ett organisationsschema. Den innehåller enskilda rapportenheter som representerar varje ruta i schemat. Enheterna kan vara antingen enskilda avdelningar från ekonomiska data eller på de enheter som sammanfattar data från andra rapportenheter. | [Rapportträddefinitioner](financial-reporting-tree-definitions.md) |
| Rapportdefinition         | Rapportdefinitionen använder en raddefinition, en kolumndefinition och valfri rapportträddefinition för att bygga upp en rapport. Den ger också ytterligare alternativ och inställningar som du kan använda för att anpassa en rapport. | [Rapportdefinition](design-financial-report-definitions.md) |

Om du är nybörjare på att utforma rapporter är det praktiskt att använda rapportguiden för att snabbt skapa en rapportdefinition som du senare kan anpassa. Om du har erfarenhet av att utforma rapporter och vill ha mer flexibilitet i rapportdesignen kan du kombinera nya eller befintliga byggblock för att skapa en ny rapportdefinition. Du behöver inte förstå alla tillgängliga rapportdefinitionsalternativ helt för att skapa kvalitetsrapporter. När du blir bekant med att utforma rapporter kan du expandera dina rapportdefinitioner och dra nytta av mer avancerade funktioner. När du har skapat en grundrapport kan du anpassa rapportdefinitionen och byggblocken i rapportdefinitionen.

## <a name="organize-the-building-blocks"></a>Ordna byggblocken
Använd mappar när du vill ordna byggblock i Report Designer. Alla mappar är specifika för den typ av byggblock de innehåller. Till exempel finns alla mapparna som innehåller raddefinitioner i fönstret **Raddefinitioner** i Report Designer.

### <a name="create-a-folder"></a>Skapa en mapp

1. I Report Designer. väljer du den typ av byggblock för att organisera i navigeringsfönstret. Om du till exempel vill sortera en raddefinition klickar du på **Raddefinitioner**
2. I navigeringsfönstret väljer du en befintlig mapp att skapa en ny mapp under och följer sedan ett av de här stegen:

    - Högerklicka på den överordnade mappen och klicka sedan på **Ny mapp**.
    - Välj den överordnade mappen, klicka på **Fil** och klicka sedan på **Ny mapp**.

3. Ange namnet på den nya mappen när den visas och tryck sedan på Retur.

## <a name="lock-a-building-block"></a>Låsa ett byggblock
Du kan skapa ett lösenord för att skydda och låsa ett byggblock. På det här sättet kan du lägga till en säkerhetsnivå till en rapportkomponent utan att behöva skydda hela systemet. Ett lösenord kan bidra till att skydda information om byggblock som är viktiga för din rapporteringsprocess i månadsslutet. En användare i en roll kan låsa ett byggblock. Andra användare har dock alltid skrivskyddad åtkomst till en låst komponent. Användarna kan öppna, ändra och spara den låsta komponenten under ett nytt namn. En användare som har rollen som administratör kan alltid komma åt och ändra ett låst byggblock.

1. I Report Designer öppnar du rapportkomponenten för att låsa till exempel en raddefinition, kolumndefinition, rapportdefinition eller rapporteringsträddefinition.
2. Gå till menyn **Verktyg** och klicka på **Skydda/ta bort skydd**. Du kan också klicka på (låsikonen) **Skydda/ta bort skydd** i verktygsfältet.
3. I dialogrutan **Skydda** ska du ange och bekräfta ett lösenord och sedan klicka på **OK**. Låsikonen i verktygsfältet är markerad när ett öppet byggblock låses.

Öppna ett låst byggblock genom att öppna byggblocket och sedan klicka på ikonen **Skydda/ta bort skydd** i verktygsfältet. Alternativt, gå till menyn **Verktyg** och klicka på **Ta bort skydd**.

## <a name="building-block-groups"></a>Byggblocksgrupper

Byggblock är de raddefinitioner, kolumndefinitioner, rapportträddefinitioner och rapportdefinitioner som du skapar för en rapport. Byggblocksgrupper är samlingar med definitioner och dimensionsgrupper.

### <a name="view-a-building-block-group"></a>Visa en byggblocksgrupp

Du kan visa alla byggblock som tilldelas en byggblockgrupp. Du kan även exportera eller importera en byggblockgrupp.

1. Klicka på **Byggblocksgrupper** på **Företag**-menyn i Report Designer.
2. I dialogrutan **Byggblockgrupper** väljer du det byggblock som ska visas.
3. Klicka på **Visa** för att öppna dialogrutan **Visa byggblocksgrupp** där du kan visa innehållet i byggblocksgruppen.
4. Klicka på **Stäng** för att stänga dialogrutan.

### <a name="export-a-building-block-group"></a>Exportera en byggblocksgrupp

Du kan exportera en byggblocksgrupp eller rapportbyggblock i en byggblocksgrupp. Du kan använda den exporterade byggblocksgruppen som en säkerhetskopia. Du kan också kopiera exporterade data mellan Finance and Operations-installationer. Rapportdesignern inkluderar de refererade teckenstilarna och dimensionsuppsättningarna tillsammans med byggblockgruppen.

1. I Report Designer, på menyn **Företag** klicka på **Byggblockgrupper**.
2. Markera det byggblock som ska exporteras i dialogrutan **Byggblocksgrupper** och klicka sedan på **Exportera**.
3. I dialogrutan **Exportera** väljer du de rapportdefinitioner som du vill exportera:

    - Klicka på **Markera alla** om du vill exportera alla dina rapportdefinitioner och de associerade byggblocken.
    - Om du vill exportera specifika rapporter, rader, kolumner, träd eller dimensionsuppsättningar klickar du på lämpliga flikar och väljer de artiklar du vill exportera. Tryck och håll ned CTRL-tangenten om du vill välja flera artiklar på en flik.

    > [!NOTE]
    > När du markerar de rapporter som ska exporteras markeras motsvarande rader, kolumner, träd och dimensionsgrupper.

4. När du har valt artiklar som ska exporteras, klicka på **Exportera**.
5. I dialogrutan **Spara som** väljer du en plats att exportera byggblockgruppen till.
6. I fältet **Filnamn** anger du ett namn för filen. Report Designer lägger automatiskt till ett .tdbx-filnamnstillägg.
7. Klicka på **Spara**. Byggblocksgruppen sparas på den plats du anger.

### <a name="import-a-building-block-group"></a> Importera en byggblockgrupp

Du kan importera en byggblockgrupp till en befintlig byggblockgrupp. Alla importerade byggblocksgrupper behåller sina ursprungliga teckensnittsinställningar och företagsreferenser och inkluderar relevanta dimensionsuppsättningar.

1. I Report Designer, på menyn **Företag** klicka på **Byggblockgrupper**.
2. Markera det byggblock som ska byggblocksgruppen ska importeras till i dialogrutan **Byggblocksgrupper** och klicka sedan på **Importera**.
3. Markera den byggblocksgrupp som ska importeras i dialogrutan **Öppna**, och klicka sedan på **Öppna**.
4. I dialogrutan **Importera** väljer du de rapportdefinitioner som du vill importera:

    - Klicka på **Markera alla** om du vill importera alla rapportdefinitioner och stödjande byggblock.
    - Om du vill importera specifika rapporter väljer du de rader, kolumner, träd eller dimensionsuppsättningar som ska importeras.

5. När du har valt artiklar att importera, klicka på **Importera**.

### <a name="undo-a-checkout-of-a-building-block"></a>Ångra en utcheckning av ett byggblock

När du öppnar ett byggblock kan andra användare bara komma åt byggblocket i skrivskyddat läge. Ibland kan en användare glömma att stänga ett byggblock eller stänger av sitt system utan att stänga byggblocket. Därför förblir byggblocket utcheckat och ingen annan användare kan öppna det. I en sådan situation kan en administratör för ekonomisk rapportering använda dialogrutan **Utcheckade artiklar** för att checka in byggblock som en användare har lämnat i utcheckad.

> [!NOTE]
> Du måste ha rollen administratör för att checka in byggblock med dialogrutan **Utcheckade objekt**.

1. I Report Designer på menyn **Verktyg** klickar du på **Utcheckade artiklar**.
2. Markera **Visa objekt från alla användare** i dialogrutan **Utcheckade objekt**. Listan uppdateras så att alla byggblock som är utcheckade och de användare som har checkat ut byggblocken visas.
3. Markera ett byggblock och klicka på **Ångra utcheckning**.
4. Klicka på **Ja** för att checka in byggblocket.

## <a name="additional-resources"></a>Ytterligare resurser

[Ekonomisk rapportering](financial-reporting-intro.md)
