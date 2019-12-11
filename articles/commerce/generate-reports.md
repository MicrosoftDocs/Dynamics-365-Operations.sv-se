---
title: Generera kanalrapporter online
description: Det här ämnet beskriver hur du genererar rapporter för din onlinekanal i Microsoft Dynamics 365 Retail.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 77737c134df8f3ba598fe9026fa7c01ca9976733
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698060"
---
# <a name="generate-online-channel-reports"></a>Generera kanalrapporter online

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här ämnet beskriver hur du genererar rapporter för din onlinekanal i Microsoft Dynamics 365 Retail.

## <a name="overview"></a>Översikt

Du kan generera och Visa flera rapporter i Retail för att se hur din kanal är online.

## <a name="channel-summary-report"></a>Kanalöversikt - rapport

I rapporten **kanalsammanfattning** visas en sammanfattning av följande transaktioner för den valda kanalen:

- Försäljningstransaktioner
- Betalningstransaktioner
- Skattetransaktioner
- Rabatterade transaktioner

För att generera **Kanalsammanfattning** följ dessa steg.

1. Gå till **Butik \> Frågor och rapporter \> Försäljningsrapporter \> Kanalöversiktsrapport**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.
 
## <a name="channel-sales-by-year-report"></a>Kanalförsäljning per år - rapport 

Rapporten **Kanalförsäljning per år** visar en jämförelse av försäljning per årsbasis för en viss butik. Du väljer året att jämföra försäljningen mot och rapporten jämför försäljningen för det valda året med försäljning för föregående år.

För att generera **Kanalförsäljning per år** följ dessa steg.

1. Gå till **Butik \> Frågor och rapporter \> Försäljningsrapporter \> Rapporten Kanalförsäljning per år**.
1. I fältet **Från kalenderår** anger du ett år.
1. I fältet **Till kalenderår** anger du ett år.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="channel-sales-by-hour-report"></a>Kanalförsäljning per timme - rapport

Rapporten **Kanalförsäljning per timme** visar försäljningsmetrik per timme för en vald kanal eller driftsenhet.

För att generera **Kanalförsäljning per timme** följ dessa steg.

1. Gå till **Butik \> Frågor och rapporter \> Försäljningsrapporter \> Rapporten Kanalförsäljning per timme**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="top-customers-report"></a>Främsta kunderna - rapport

Rapporten **De främsta kunderna** visar försäljningsmått för de *N* främsta kunderna för en vald kanal eller driftenhet. Värdet *N* är ett tal mellan 10 och 100 och baseras på en användardefinierat sammanlagt mått.

För att generera rapporten **De främsta kunderna** följ dessa steg.

1. Gå till **Butik \> Frågor och rapporter \> Försäljningsrapporter \> Rapporten De främsta kunderna**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="top-discounts-report"></a>Rapport över topprabatter

Rapporten **topprabatter** visar försäljningsmått för de *N* rabatter för en vald kanal eller driftenhet. Värdet *N* är ett tal mellan 10 och 100 och baseras på en användardefinierat sammanlagt mått.

För att generera rapporten **Topprabatter** följ dessa steg.

1. Gå till **Butik \> Frågor och rapporter \> Försäljningsrapporter \> Rapporten topprabatter**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="top-products-report"></a>Rapport över topprodukter

Rapporten **topprodukter** visar försäljningsmått för de *N* produkter för en vald kanal eller driftenhet. Värdet *N* är ett tal mellan 10 och 100 och baseras på en användardefinierat sammanlagt mått.

För att generera rapporten **Topprodukter** följ dessa steg.

1. Gå till **Butik \> Frågor och rapporter \> Försäljningsrapporter \> Rapporten topprodukter**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="category-sales-report"></a>Kategoriförsäljning - rapport

Rapporten **kategoriförsäljning** visas försäljningsstatistik över en vald period för varje nod i en kategorihierarki för en vald kanal eller driftenhet.

För att generera rapporten **Kategoriförsäljning** följ dessa steg.

1. Gå till **Butik \> Förfrågningar och rapporter \> Försäljningsrapporter \> Kategoriförsäljning – rapport**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. I fältet **kanal** väljer du onlinekanal.
1. Välj **OK**.

## <a name="organization-sales-report"></a>Organisationsförsäljning - rapport

Rapporten **organisationsförsäljning** visar dina butikers resultat efter organisationsenhet. Den här rapporten inkluderar försäljningskvantitet och belopp per butik och vinst marginalen för varje butik. Organisationsenheten baseras på standardhierarkin för rapporter.

För att generera rapporten **Organisationsförsäljning** följ dessa steg.

1. Gå till **Butik \> Förfrågningar och rapporter \> Försäljningsrapporter \> Organisationsförsäljning – rapport**.
1. I fältet **Från datum** anger du ett datum.
1. I fältet **Till-datum**, anger du ett datum.
1. Välj **OK**.

## <a name="additional-resources"></a>Ytterligare resurser

- [Hjälpresurser för Dynamics 365 Retail](../retail/index.md)
