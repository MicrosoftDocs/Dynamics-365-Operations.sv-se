---
title: "Skapa kuponger för butiksförsäljning"
description: "Det här avsnittet innehåller en översikt över butikskuponger och hur du ställer in dem."
author: scott-tucker
manager: AnnBe
ms.date: 05/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailCoupon, RetailParameters, RetailSharedParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: scotttuc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9b4e792cae66e38546b3bdfdfbd59a2e36d891c2
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="create-coupons-for-retail-sales"></a>Skapa kuponger för butiksförsäljning

[!include [banner](includes/banner.md)]

## <a name="overview-of-coupons"></a>Översikt över kuponger

Kuponger är koder och streckkoder som används för att lägga till butiksrabatter till transaktioner. Varje kupong kan ha flera koder och varje kod kan ha sitt eget giltighetsdatum. 

Varje kupong är kopplad till en butiksrabatt. Prisgrupper som associeras med rabatten definierar vilka kunder som kan använda en kupong eller kanaler där en kupong är giltig. 

I princip är kuponger extra validering utöver butikskuponger. Kupongen innehåller de kupongkoder och streckkoder som krävs samt datumintervall för dessa koder. Kupongen ger dessutom valfria användningsbegränsningar och villkor som ska uppfyllas av kunden. Rabatten innehåller de produkter som gäller för kupongen. Prisgrupper för rabatten innehåller uppsättningen med kunder, kanaler eller kataloger som kupongen gäller för.

Om du vill skapa en kupong skapar du rabatten och kupongen separat. Du kan sedan länka dem genom att välja en rabatt på sidan Kupong i Microsoft Dynamics 365 for Retail. 

> [!NOTE]
> När en kupong är länkad till en rabatt blir flera fält i Microsoft Dynamics 365 for Retail skrivskyddade, eftersom de hanteras av inställningen för kupongen. Fälten inkluderar fält för status och standarddatumintervall.

### <a name="limited-use-coupons"></a>Kuponger med begränsad användning

Du kan konfigurera kuponger som kuponger med begränsad användning. Användningsgränsen kan definieras per kund eller kanal, eller som en global begränsning. Denna begränsning gäller när koden eller streckkoden används eller skannas i kassan eller vid registrering av försäljningsorderposten.

Gränsen tillämpas per kupongkod på en kupong. Exempelvis kan en kupong med två kupongkoder användas två gånger: en gång för varje kupongkod. Varje kod i en kupong aktiveras oberoende av varandra.

> [!NOTE]
> När en kupongkod har nått sin användningsgräns ändrar systemet *inte* automatiskt status för kupongkoden till ”använd”. Systemet tillåter emellertid inte ytterligare användning av kupongkod som har nått sin användningsgräns. Om status för en kupongkod anges manuellt till något förutom ”aktiv” kan inte denna kupongkod användas i någon kanal.

## <a name="managing-coupons"></a>Hantera kuponger

Du måste skapa rabatten och kupongen separat. Sedan länkar du dem genom att välja en rabatt på sidan Kupong. När du har länkat en kupong till en rabatt blir flera fält i rabatt skrivskyddade, eftersom de hanteras av inställningarna för kupongen. Fälten inkluderar fält för status och standarddatumintervall.  

I princip är kuponger nu extra validering utöver butikskuponger. Kupongen innehåller kupongkoder och streckkoder, datumintervall, användningsbegränsningar och villkor som kunden måste uppfylla. Rabatten innehåller de produkter som gäller för kupongen. Rabattprisgrupper innehåller uppsättningen kunder, kanaler eller kataloger som kupongen gäller för.

## <a name="system-setup-for-coupons"></a>Systeminställning för kuponger 

Innan du kan skapa en kupong måste du ställa in kupongens streckkod och två kupongnummerserier. 

1.  På sidan **Masktecken** skapas ett nytt masktecken för kupongkoden. Du kan välja ett valfritt oanvänt tecken.
2.  På sidan **Inställning av streckkodsmask** ska du skapa en ny streckkodsmask. Ställ in fältet **Typ** på **Kupong**.
3.  På sidan **Streckkodsinställning** skapar du en ny streckkod som använder streckkodsmasken som du just skapade.
4.  På sidan **Nummerserier** skapar du två nya nummerserier. En serie för kupongkods-ID och en annan för kupongnummer. Kupongkods-ID är den unika identifieraren för varje kupongkod för en kupong. Kupongnumret är den unika identifierare för en kupong. Varje kupong kan ha flera koder och streckkoder som aktiverar kupongen.

    > [!NOTE]
    > För de båda nummerserierna måste du ställa in fältet **Omfattning** på **Företag**. I de flesta fall ska du generera båda nummerserienumren automatiskt.

5.  På sidan **Butiksparametrar** på fliken **Streckkoder**, välj streckkoden som du skapade tidigare.
6.  På sidan **Delade butiksparametrar** på fliken **Nummerserier** väljer du de nummerserier som du skapade för kupongnummer och kupongkods-ID.
7.  Du kan nu öppna sidan **Kupong** och skapa nya kuponger.

## <a name="the-effect-of-partial-updates-on-coupons"></a>Effekten av ofullständiga uppdateringar av kuponger

Kupongfunktionen omfattar flera olika funktioner i Dynamics 365 for Retail. Microsoft Dynamics 365 för Retail headquarters (huvudkontor) och kanalen kan delvis uppdateras över komponenter. Därför är det viktigt att du förstår hur ofullständiga uppdateringar påverkar kupongens funktion i sin helhet.

- **Huvudkontor är delvis uppdaterat, men Butik och Kassa är inte uppdaterade.** Vid uppdatering av Huvudkontor uppdateras sidorna Kupong och Rabatt. Även motorn för butikspris uppdateras. Om endast en av dessa två komponenter uppdateras kommer vissa sidor i Butik inte att matcha prisberäkningsdata. Därför kan oväntade rabattberäkningar eller fel inträffa vid beräkningarna av rabatten.
- **Huvudkontor är uppdaterat, men Butik-servern och Kassa är inte uppdaterade (N-1).** Eftersom inte alla butiker kan uppdateras samtidigt, rekommenderar vi att du uppdaterar huvudkontoret innan du uppdaterar butiker. I N-1-scenariot kommer inte nya funktioner som är relaterade till kuponger att visas i butiker som ännu inte har uppdaterats. Exempelvis introducerar kuponger funktionen ”Uteslut”-rader. Om du använder utelämnar rader på en rabatt, används de inte i butiker som kör en tidigare version.
- **Huvudkontor är inte uppdaterat, men Butik-servern och Kassa är inte uppdaterade (N+1).** Eftersom prismotorn är uppdaterad i Butik kan servern hantera äldre rabattkoder under prisberäkningar. Uppdateringen bör inte ha någon funktionspåverkan i det här scenariot.

