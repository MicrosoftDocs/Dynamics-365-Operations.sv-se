---
title: Generera kanalrapporter online
description: Det här ämnet beskriver hur du genererar rapporter för din onlinekanal i Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 80d62b29fcc95a3153c604512e1ee6b3e55ba840
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019797"
---
# <a name="generate-online-channel-reports"></a>Generera kanalrapporter online

[!include [banner](includes/banner.md)]

Det här ämnet beskriver hur du genererar rapporter för din onlinekanal i Microsoft Dynamics 365 Commerce.

Du kan generera och Visa flera rapporter i Commerce för att se hur din kanal är online.

## <a name="channel-summary-report"></a>Kanalöversikt – rapport

I rapporten **kanalsammanfattning** visas en sammanfattning av följande transaktioner för den valda kanalen:

- Försäljningstransaktioner
- Betalningstransaktioner
- Skattetransaktioner
- Rabatterade transaktioner

För att generera **Kanalsammanfattning** följ dessa steg.

1. Gå till **Butik och handel \> Frågor och rapporter \> Försäljningsrapporter \> Kanalöversiktsrapport**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.
 
## <a name="channel-sales-by-year-report"></a>Kanalförsäljning per år – rapport 

Rapporten **Kanalförsäljning per år** visar en jämförelse av försäljning per årsbasis för en viss butik. Du väljer året att jämföra försäljningen mot och rapporten jämför försäljningen för det valda året med försäljning för föregående år.

För att generera **Kanalförsäljning per år** följ dessa steg.

1. Gå till **Butik och handel \> Frågor och rapporter \> Försäljningsrapporter \> Kanalförsäljning per år – rapport**.
1. I fältet **Från kalenderår** anger du ett år.
1. I fältet **Till kalenderår** anger du ett år.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="channel-sales-by-hour-report"></a>Kanalförsäljning per timme – rapport

Rapporten **Kanalförsäljning per timme** visar försäljningsmetrik per timme för en vald kanal eller driftsenhet.

För att generera **Kanalförsäljning per timme** följ dessa steg.

1. Gå till **Butik och handel \> Frågor och rapporter \> Försäljningsrapporter \> Kanalförsäljning per timme – rapport**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="top-customers-report"></a>Främsta kunderna – rapport

Rapporten **De främsta kunderna** visar försäljningsmått för de *N* främsta kunderna för en vald kanal eller driftenhet. Värdet *N* är ett tal mellan 10 och 100 och baseras på en användardefinierat sammanlagt mått.

För att generera rapporten **De främsta kunderna** följ dessa steg.

1. Gå till **Butik och handel \> Frågor och rapporter \> Försäljningsrapporter \> Främsta kunderna – rapport**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="top-discounts-report"></a>Rapport över topprabatter

Rapporten **topprabatter** visar försäljningsmått för de *N* rabatter för en vald kanal eller driftenhet. Värdet *N* är ett tal mellan 10 och 100 och baseras på en användardefinierat sammanlagt mått.

För att generera rapporten **Topprabatter** följ dessa steg.

1. Gå till **Butik och handel \> Frågor och rapporter \> Försäljningsrapporter \> Rapport över topprabatter**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="top-products-report"></a>Rapport över topprodukter

Rapporten **topprodukter** visar försäljningsmått för de *N* produkter för en vald kanal eller driftenhet. Värdet *N* är ett tal mellan 10 och 100 och baseras på en användardefinierat sammanlagt mått.

För att generera rapporten **Topprodukter** följ dessa steg.

1. Gå till **Butik och handel \> Frågor och rapporter \> Försäljningsrapporter \> Rapport över topprodukter**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="category-sales-report"></a>Kategoriförsäljning – rapport

Rapporten **kategoriförsäljning** visas försäljningsstatistik över en vald period för varje nod i en kategorihierarki för en vald kanal eller driftenhet.

För att generera rapporten **Kategoriförsäljning** följ dessa steg.

1. Gå till **Butik och handel \> Förfrågningar och rapporter \> Försäljningsrapporter \> Kategoriförsäljning – rapport**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="organization-sales-report"></a>Organisationsförsäljning – rapport

Rapporten **organisationsförsäljning** visar dina resultat efter organisationsenhet. Den här rapporten inkluderar försäljningskvantitet och belopp per butik och vinst marginalen för varje butik. Organisationsenheten baseras på standardhierarkin för rapporter.

För att generera rapporten **Organisationsförsäljning** följ dessa steg.

1. Gå till **Butik och handel \> Förfrågningar och rapporter \> Försäljningsrapporter \> Organisationsförsäljning – rapport**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. Välj **OK**.

## <a name="additional-resources"></a>Ytterligare resurser

- [Startsidan för Commerce](./index.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]