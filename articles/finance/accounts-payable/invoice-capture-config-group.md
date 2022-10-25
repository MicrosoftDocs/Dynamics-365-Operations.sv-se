---
title: Lösningen Invoice Capture konfigurationsgrupper
description: Den här artikeln innehåller allmän information om hur konfigurationsgrupper ställs in i lösningen Invoice Capture.
author: sunfzam
ms.date: 09/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cfe5ae35b4f87a350d944b30a49251081766ad27
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691222"
---
# <a name="invoice-capture-solution-configuration-groups"></a>Lösningen Invoice Capture konfigurationsgrupper

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Användarna kan hantera listan med fakturafält och den manuella granskningsinställningen för juridiska personer genom att använda konfigurationsgrupper. Användare kan ställa in fakturakonfigurationer för olika juridiska personer i grupper. Alla juridiska personer i samma konfigurationsgrupp använder samma fakturafält och inställningar för manuell granskning.

## <a name="manage-configuration-groups"></a>Underhåll konfigurationsgrupper

För att hantera konfigurationsgrupper med hjälp av appen, gå till **Inställningar** och väljer **Systeminställningar \> Definiera innehåll för konfigurationsgrupper**.

På sidan **Definiera konfigurationsgrupper** visas huvudfliken listan över konfigurationsgrupper som har definierats. Här visas också en standardkonfigurationsgrupp. För varje konfigurationsgrupp är följande åtgärder tillgängliga:

- **Kopiera en konfigurationsgrupp** – Du kan skapa en ny konfigurationsgrupp genom att duplicera en befintlig grupp. Den nya gruppen har samma värden som originalgruppen för alla fält utom **Gruppnamn** och **Gruppbeskrivning**. När konfigurationsgruppen har duplicerats väljer du **OK**.
- **Ta bort konfigurationsgrupper** – Om du vill ta bort en konfigurationsgrupp markerar du den och väljer sedan **Ta bort**.

    > [!NOTE]
    > Standardkonfigurationsgruppen kan inte tas bort.

- **Redigera en konfigurationsgrupps ID** – Om du vill redigera ID:t för en konfigurationsgrupp väljer du **grupp-ID** fältet och uppdaterar värdet. Grupp-ID:t får inte innehålla blanksteg eller specialtecken och får inte innehålla fler än 20 tecken.

    > [!NOTE]
    > Värdet i fältet **Grupp-ID** kan endast uppdateras en gång.

- **Redigera en konfigurationsgrupps beskrivning** – Om du vill redigera beskrivningen för en konfigurationsgrupp väljer du **Beskrivning** fältet och uppdaterar värdet.
- **Ändra inställningen för manuell granskning** – Användarna kan bestämma om en faktura ska granskas manuellt. Om du vill ändra inställningen för manuell granskning väljer du alternativet **Behov av manuell granskning**. Följande alternativ är tillgängliga:

    - **Alltid manuell granskning** – Välj det här alternativet om fakturor i konfigurationsgruppen alltid kräver manuell granskning.
    - **För fel och varningar** – Välj det här alternativet om fakturor som innehåller felmeddelanden eller varningsmeddelanden kräver manuell granskning.
    - **För fel** – Välj det här alternativet om fakturor som innehåller felmeddelanden kräver manuell granskning.

- **Ändra inställningen för förtroenderesultat** – Förtroenderesultatet är metadata som lösningen Invoice Capture ger för att rapportera noggrannheten för kända fakturadata. Ju högre poäng det är, desto mer exakt kan de kända data vara. Med konfigurationen kan användarna definiera när manuell granskning krävs, baserat på konfidenspoäng. Användare kan ändra tröskelvärdet för konfidenspoäng för fakturor. Om du vill uppdatera inställningen för konfidenspoäng väljer du fältet **konfidenspoäng** och uppdaterar värdet.

    Det finns två notifieringstyper för konfidenspoäng:

    - **Varning** – Fakturafält som har konfidenspoäng över varningströskeln betraktas som korrekta. Varningströskeln måste vara större än feltröskeln och vara lägre än 100.
    - **Fel** – Fakturafält som har konfidenspoäng under feltröskeln betraktas som misslyckade. Felmeddelanden visas för användaren. Feltröskeln måste vara större än 0 (noll) och mindre än varningströskeln. Varningsmeddelanden visas för fakturafält som har konfidenspoäng mellan varningströskeln och feltröskeln.

- **Hantera fakturafält** – Användarna kan hantera listan med fakturafält som visas i visningsprogrammet sida vid sida. På fliken **Fakturafälthantering** välj kugghjulssymbolen, välj de fakturafält som ska läggas till och välj sedan **Spara**. De valda fälten kommer att läggas till i listan. Om du vill ta bort ett fakturafält från listan väljer du **Ta bort** i fältet.

### <a name="manage-file-filters-optional"></a>Hantera filfilter (valfritt)

Med Hantera filfilter kan användare definiera ytterligare filter för inkommande fakturafiler. Filer som inte uppfyller filterkriteriet tas emot och visas i listan **Mottagna filer**, men de kommer att visa filvalideringsfel. Det här beteendet skiljer sig från beteendet för filter som har definierats i kanalen. För dessa filter tas filer som inte uppfyller kriterierna inte emot alls. Användare kan granska de inkommande filerna och avgöra om varje fil är en ogiltig faktura och filen kan vara föråldrad eller manuellt inkludera den för igenkänning och inkludering i registrerade fakturor.

När lösningen Invoice Capture har installerats definieras ett standardfilfilter. Det här filfiltret är globalt. Om du vill ha andra filterinställningar kan du uppdatera standardfiltret. Om ett fält är obligatoriskt väljer du **Obligatoriskt**. 

### <a name="accepted-file-size"></a>Godkänd filstorlek

Du kan välja den godkända filstorleken.

> [!NOTE]
> Filer som är större än 20 480 kilobyte (KB) stöds inte.

### <a name="supported-file-types"></a>Filtyper som stöds

Följande filtyper av sammanfogningar stöds nu:

- PDF
- PNG
- JPG
- JPEG
- TIF
- TIFF
