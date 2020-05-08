---
title: Skapa avancerade kontrakt för fakturering baserat på status
description: I det här avsnittet beskrivs hur du skapar projektkontrakt så att du kan skapa fakturor för kunder, baserat på en procentsats av färdigt arbete.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282849"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a>Skapa avancerade kontrakt för fakturering baserat på status
[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du skapar projektkontrakt så att du kan skapa fakturor för kunder, baserat på en procentsats av färdigt arbete. Fakturabeloppen beräknas automatiskt för budgetkategorier av arbete som du anger för ett projekt. Tajmingen med fakturor har ställts in, när du förhandlar projektkontraktet till kunden.

Använd förfaranden i detta avsnitt om du vill ställa in ett kontrakt, ett associerat projekt och ett faktureringsreglerna för att beräkna fakturabelopp för budgetkategorier, av arbete som du anger för projektet.

När du har skapat kontraktet och projekt, kan du ställa in information om projektet. Du kan till exempel definiera aktiviteterna och tilldela anställda till projektet.

## <a name="example"></a>Exempel

Din organisation är en firma för programvaruutveckling. Du går med på att sammanställa ett lönelista redovisningpaket för en kund för en total kostnad av 20 000 USD. Organisationen förbinder sig att fakturera kunden när du slutför de specifika procentandelarna av projektet. Du ställer in följande projektkategorier för arbetet så att du kan använda dem i faktureringsprocessen:

- Konsultarbete
- Design
- Installation

Du ställer också in faktureringsregler som automatiskt beräknar fakturabelopp för procent av projektarbete, som utförs för varje kategori.

Budgetchefen skapar en budget för projektkategorier. Beloppet för slutfört arbete beräknas automatiskt som en procentandel av faktiskt arbete jämfört med budgeterade belopp.

## <a name="prerequisites"></a>Förutsättningar

Innan du skapar ett projekt som använder faktureringsregler måste du ställa in nummer serier för faktureringsregler och en avgiftsjournal som används för att bokföra förfallna faktureringar.

1. Gå till **Projektledning och redovisning** \> **Inställningar** \> **Parametrar för projekthantering och redovisning**.
2. På sidan **Parametrar för projekthantering och redovisning** på fliken **nummer serier** på sidan projekthantering och redovisningsparametrar.
3. Gå till **Projekthantering och redovisning** \> **Journaler** \> **Avgift**.
4. På sidan **Avgiftsjournal**, välj **Ny** och ange journalnamnet.

## <a name="create-a-contract-for-progress-billings"></a>Skapa ett kontrakt för delfakturering

Använd den här proceduren för att skapa en projektkontrakt för ett fastprisprojekt. Du skapar en projektfaktura när utfört arbetet på projektet, når en viss procent.

1. Gå till **Projekthantering och redovisning** \> **Projekt** \> **Projektkontrakt**.
2. Välj **Projektkontrakt** på sidan **Leveranssätt**.
3. I dialogrutan **nytt projektkontrakt** anger du följande fält:

    - **Namn**
    - **Finansieringstyp**
    - **Finansieringskälla**
    - **Försäljningsvaluta** – som standard används denna valuta för kundfakturor som är kopplade till projektkontraktet. Du kan dock ändra försäljningsvaluta för en viss kundfaktura.

4. Välj **OK**. Informationen kopieras till huvudet på sidan **Projektkontrakt**.
5. På sidan **Projektkontrakt** fyll i resten av den information som krävs för projektet.

## <a name="create-a-project-for-progress-billings"></a>Skapa ett projekt för delfakturering

Följ dessa steg för att skapa ett projekt och alla delprojekt som är associerade med ett projektkontrakt.

1. Gå till **Projekthantering och redovisning** \> **Projekt** \> **Alla projekt**.
2. På sidan **Alla projekt**, välj **Ny**.
3. I dialogrutan **Nytt projekt** i fältet **Projekttyp**, välj **Tid och material**.
4. Välj en projektgrupp En projektgrupp definierar bokföringsinformation för projekt som tilldelats gruppen.
5. Markera **Skapa projekt**.
6. Ange projektfasen till **Pågår** efter att du har skapat projektet.

## <a name="create-a-budget-for-a-project"></a>Skapa en budget för ett projekt

Budgetkategorierna används för att beräkna automatiskt fakturabeloppen för procent av arbete som utförs för varje kategori. Skapa budgetkategorier för de uppskattade kostnaderna genom att följa stegen nedan.

1. Gå till **Projekthantering och redovisning** \> **Projekt** \> **Alla projekt**.
2. På sidan **Alla projektet**, välj och öppna det projekt du vill.
3. På sidan **Projekt** i åtgärdsfönstret **Plan** i gruppen **Budget**, välj **Projektbudget**.
4. På sidan **Projektbudget** ange en uppskattad kostnad för varje kategori i projektet.

## <a name="create-billing-rules-for-progress-billings"></a>Skapa faktureringsregler för delfakturering

1. Gå till **Projekthantering och redovisning** \> **Projekt** \> **Projektkontrakt**.
2. På sidan **projektkontrakt** väljer du och öppnar ett projektkontrakt.
3. På sidan projektkontrakt, på snabbfliken **faktureringsregler**, välj **Lägg till**.
4. På sidan **Faktureringsregel** i fältet **Radtyp**, välj **Förlopp**.
5. På snabbfliken **Information om faktureringsregelrad** i fältet **kontraktsvärde**, ange kontraktets totala värde.
6. Välj kategori att bokföra avgiftstransaktionen till i fältet **kategori**.
7. Välj det projekt eller den uppgift som använder den här faktureringsregeln i fältet **projekt**.
8. Valfritt: Tilldela faktureringsregeln till ytterligare projekt. På snabbfliken **Projekt** i avsnittet **Tillgängliga projekt**, välj ett projekt och välj sedan högerpilen för att lägga till projektet i avsnittet **Valda projekt**.
9. Valfritt: Beräkna procentbeloppet som kunden innehåller från betalningar i en faktura. På snabbfliken **Villkor för innehållen betalning**, välj finansieringskällan och sedan i fältet **kvarhållandeprocentsats**, ange kvarhållandeprocentsatsen.
10. Upprepa dessa steg för att skapa ytterligare faktureringsregler för projektkontraktet.
