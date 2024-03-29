---
title: Ställ in standardbeskrivningar för automatisk bokföring
description: Den här artikeln förklarar hur du kan ställa in standardtext som används för att beskriva redovisningsposter som bokförs automatiskt i redovisningen. Du kan ställa in standardbeskrivningstext genom att använda fritext eller välja fasta variabler.
author: aprilolson
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 71982a7d5b1bb08d3e238646ea0b15f17260bdcc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904511"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a>Ställ in standardbeskrivningar för automatisk bokföring

[!include [banner](../includes/banner.md)]

Den här artikeln förklarar hur du kan ställa in standardtext som används för att beskriva redovisningsposter som bokförs automatiskt i redovisningen. Du kan ställa in standardbeskrivningstext genom att använda fritext eller välja fasta variabler.

> [!NOTE]
> För vissa typer av transaktioner i vissa länder eller regioner kan du även ta med text från fält i som rör dessa transaktionstyper. En lista över transaktionstyperna, samt länderna och regionerna, finns i avsnittet [Valfritt: Lägg till annan text i standardbeskrivningar](#optional-add-other-text-to-default-descriptions) senare i den här artikeln.

## <a name="set-up-default-descriptions"></a>Ställ in standardbeskrivningar

1. Gå till **Organisationsadministration** \> **Inställningar** \> **Standardbeskrivningar**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. Välj transaktionstyp att skapa en standardbeskrivning för i fältet **Beskrivning**.
4. Välj språk som gäller för denna beskrivning i fältet **Språk**.
5. Ange en standardbeskrivning av artikeln i fältet **Text**. Du kan ange text i fältet, eller använda en eller flera av följande fritextvariabler:

    - **%1** – Lägg till transaktionsdatumet.
    - **%2** – Lägg till en identifierare som motsvarar dokumenttypen som bokförs i redovisningen. Till exempel för transaktionstyper, som är relaterade till fakturor, lägger variabeln **%2** till fakturanumret.
    - **%3** – Lägg till en identifierare som relaterar till dokumenttypen som bokförs i redovisningen. Till exempel för transaktionstyper som är relaterade till fakturor lägger variabeln **%3** till kundkontonumret.

## <a name="optional-add-other-text-to-default-descriptions"></a>Du kan även: Lägg till annan text i standardbeskrivningar

För vissa typer av transaktioner i vissa länder/regioner kan du även ta med text i din standardbeskrivning från fält i dina data som rör dessa transaktionstyper. Följande lista visar de transaktionstyper och länder och regioner som det här alternativet är tillgängligt för.

**Transaktionstyper**

Du kan lägga till annan text till standardinställningbeskrivningar för transaktionstyper som är relaterade till följande dokumenttyper:

- Kundfakturor
- Kundkreditfakturor
- Kundkontantbetalningar
- Leverantörsbetalningar
- Försäljningsorder
- Inköpsorder
- Lagerjournaler
- Huvudplanering (MPS)
- Anläggningstillgångar

**Länder och regioner**

Det här alternativet finns bara för följande länder och regioner:

- Brasilien
- Kina
- Tjeckien
- Östeuropa
- Ungern
- Indien
- Japan
- Litauen
- Lettland
- Polen
- Ryssland

### <a name="add-text-to-default-descriptions"></a>Lägga till text i standardbeskrivningar

När du har slutfört stegen i avsnittet [Ange standardbeskrivningar](#set-up-default-descriptions) tidigare i detta avsnitt följer du dessa steg för att lägga till annan text i standardbeskrivningarna.

1. På snabbfliken **Parametrar** väljer du **Lägg till**.
2. Välj databasregistret från vilket du vill lägga till parameterdata i beskrivningen i fältet **Referenstabell**.
3. Välj fältet från vilket du vill lägga till parameterdata i beskrivningen i fältet **Referensfält**.
4. Upprepa steg 1 till och med 3 om du vill lägga till fler parametrar.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
