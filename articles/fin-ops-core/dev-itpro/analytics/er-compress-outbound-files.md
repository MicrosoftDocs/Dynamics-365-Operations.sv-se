---
title: Komprimera stora dokument som genereras i elektronisk rapportering
description: Den här artikeln innehåller information om hur du komprimerar stora dokument som genereras av ett format för elektronisk rapportering (ER).
author: kfend
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 58771
ms.assetid: ''
ms.search.form: EROperationDesigner, ERFormatDestinationTable
ms.openlocfilehash: ebdd84cdf39e21bf3d4721b1f1545b29fe38440b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273291"
---
# <a name="compress-large-documents-that-are-generated-in-electronic-reporting"></a>Komprimera stora dokument som genereras i elektronisk rapportering 

[!include [banner](../includes/banner.md)]

Du kan använda det [ramverket för elektronisk rapportering (ER)](general-electronic-reporting.md) för att konfigurera en lösning som hämtar transaktionsdata för att generera ett utgående dokument. Det genererade dokumentet kan vara ganska stort. När den här typen av dokument genereras [används AOS-minnet (programobjektservern)](../dev-tools/access-instances.md#location-of-packages-source-code-and-other-aos-configurations) för att förvara det. Vid något tillfälle måste dokumentet hämtas från din Microsoft Dynamics 365 Finance-app. För närvarande är den maximala storleken för ett enstaka dokument som genereras i ER till 2 gigabyte (GB). Dessutom [begränsar](https://fix.lcs.dynamics.com/Issue/Details?kb=4569432&bugId=453907&dbType=3) Finance för närvarande storleken på en hämtad fil till 1 GB. Därför måste du konfigurera en ER-lösning som minskar sannolikheten för att dessa begränsningar överskrids och att du får undantaget **Strömmen var för lång**, eller som **Överfyllnad eller underfyllnad i den aritmetiska operationen**.

När du konfigurerar en lösning kan du justera ditt ER-format i operationsdesigner genom att lägga till ett rotelement i typen **Mapp** för att komprimera innehållet som genereras av något av dess kapslade element. Komprimeringen fungerar "i rätt tid", så att högsta minnesanvändning och storleken på den fil som ska hämtas kan minskas.

> [!NOTE]
> Filkomprimering tar ytterligare en andel CPU-användning.

Om du vill veta mer om den här metoden slutför du exemplet i den här artikeln.

## <a name="example-compress-an-outbound-document"></a>Exempel: komprimera ett utgående dokument

I det här exemplet visas hur en användare som tilldelats rollen **Systemadministratör** eller **Konsult för funktionen för elektronisk rapportering** kan konfigurera ett ER-format för att komprimera ett genererat dokument.

### <a name="prerequisites"></a>Förutsättningar

Innan du slutför procedurerna i detta ämne måste följande steg vara slutförda.

1. [Aktivera en konfigurationsprovider](er-defer-xml-element.md#activate-a-configuration-provider).
2. [Importera ER-exempelkonfigurationer](er-defer-xml-element.md#import-the-sample-er-configurations).
3. [Granska det importerade formatet](er-defer-xml-element.md#review-the-imported-format).

> [!NOTE]
> För närvarande startar formatstrukturen från elementet **rapport** för typen **Fil** och innehåller XML-element. Därför kommer ett utgående dokument att genereras i XML-format och ingen komprimering används.

### <a name="generate-an-er-format-to-get-an-uncompressed-document"></a>Generera ett ER-format för att hämta ett okomprimerat dokument

1. [Kör det importerade formatet](er-defer-xml-element.md#run-the-imported-format).
2. Observera att storleken på det genererade dokumentet i XML-format är 3 kilobyte (KB).

    ![Förhandsversion av det okomprimerade utgående dokumentet.](./media/er-compress-outbound-files1.png)

### <a name="modify-the-format-to-compress-the-generated-output"></a>Ändra formatet för att komprimera genererade utdata

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Modell för att lära dig uppskjutna element**.
3. Välj konfigurationen av **Format för att lära dig uppskjutna XML-element**.
4. Välj **Designer** för att ändra formatstrukturen.
5. På sidan **Formatdesigner** på fliken **Format**, välj **Lägg till rot** för att lägga till rotformatelement.
6. I dialogrutan **Lägg till** välj **Gemensam\\Mapp**.
7. Klicka på **OK** för att bekräfta att det nya rotelementet ska läggas till.
8. Välj **Spara**.

> [!NOTE]
> Formatstrukturen börjar med element av typen **Mapp**. Det här elementet genererar utdata som en komprimerad fil (zip). När ett dokument som genereras av elementet **rapport** placeras i en utgående zip-fil, komprimeras dess innehåll för att minska storleken på den utgående filen.

### <a name="generate-an-er-format-to-get-a-compressed-document"></a>Generera ett ER-format för att hämta ett komprimerat dokument

1. Välj **Formatdesigner** på sidan **Kör**.
2. Hämta zip-filen som webbläsaren erbjuder och öppna den för granskning.
3. Observera att storleken på det genererade dokumentet i ZIP-format är 1 KB.

    > [!NOTE] 
    > Komprimeringsförhållandet för XML-filen som den här zip-filen innehåller är 87 procent. Komprimeringsförhållandet beror på vilka data som komprimeras.

    ![Förhandsversion av det komprimerade utgående dokumentet.](./media/er-compress-outbound-files2.png)

> [!NOTE]
> Om ER [destinationen](electronic-reporting-destinations.md) har konfigurerats för det formatelement som genererar utdata (elementet **rapport** i det här exemplet), kommer komprimeringen av utdata att kringgås.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)

[Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)

[Skjuta upp körningen av XML-element i ER-format](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
