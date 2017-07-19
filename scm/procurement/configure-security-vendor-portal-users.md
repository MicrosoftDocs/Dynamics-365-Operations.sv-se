---
title: "Användarsäkerhet för leverantörportal"
description: "Den här artikeln innehåller information om hur du konfigurerar säkerhet för externa leverantörer som använder leverantörsportalen. Denna information gäller endast Dynamics AX-versionerna från februari 2016 &amp; maj 2016."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 560e0760c33cab4186095ac2ae7e105d75cc16d0
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017

---

# <a name="vendor-portal-user-security"></a>Användarsäkerhet för leverantörportal

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller information om hur du konfigurerar säkerhet för externa leverantörer som använder leverantörsportalen. Denna information gäller endast Dynamics AX-versionerna från februari 2016 &amp; maj 2016.

Funktionen för leverantörsportal har ersatts med utökade funktioner för leverantörsamarbeten i Dynamics 365 for Operations, version 1611. Mer information om hur du konfigurerar säkerheten för leverantörssamarbeten finns i [Skapa och underhålla leverantörssamarbete](set-up-maintain-vendor-collaboration.md). Säljaren portal utsätter en begränsad uppsättning information om inköpsorder (POs) till externa leverantörer. Det är viktigt att du korrekt konfigurera användarbehörigheter för säljaren portal i Microsoft Dynamics AX, så att leverantörerna inte har oavsiktlig åtkomst till ytterligare information i ditt Dynamics AX installation. **Viktigt!** Till skillnad från andra användare, externa leverantörer bör inte ha **SystemUser** roll. Det **SystemUser** roll ger tillgång till en uppsättning rättigheter som inte är lämpliga för externa användare.

## <a name="setting-up-a-vendor-portal-user"></a>Ställa in en leverantör portal-användare
Innan du skapar ett användarkonto för någon som använder säljaren portalen måste du ställa upp säljaren att säljaren portal samarbete. Använd **inköpsorder samarbete** på **fliken Allmänt** på **leverantörer** . Externa leverantörer som använder säljaren portal måste ha följande inställningar:

-   En Microsoft Azure Active Directory (AAD) användarkonto måste registreras för säljaren på **användare** i Dynamics AX.
-   Säljaren måste **säljaren (extern)** säkerhet roll, inte **SystemUser**roll. **Obs!** **SystemUser** roll beviljas automatiskt när du skapar ett nytt användarkonto i Dynamics AX. Därför måste du ta den rollen och bekräfta varningsmeddelandet som du tar emot.
-   Säljaren bör inte beviljas tillstånd för att lägga till ytterligare fält från PO bord till deras uppfattning av PO. På **fliken anpassning** , på **fliken Användare** , ange**uttryckliga anpassningen tillåtet** alternativ för användaren till **någon**.
-   Användaren måste vara kopplad till en registrerad kontaktperson. Om **användarna** väljer du en kontaktperson i **fältet Namn** . Den person som du väljer bör ha **kontakt** roll för respektive leverantör.

Om samma person kräver tillgång till säljaren portal för flera leverantörer konton (för olika juridiska enheter, kanske), varje personens användarkontona måste vara associerade med samma registrerade kontaktperson. **Säljaren (extern)** roll innefattar alla de grundläggande funktioner som krävs för att använda funktionerna som är tillgängliga i säljaren portal. Den här installationen hjälper till att säkra att användargränssnittet att externa användare ser är fokuserade på den avsedda scenario.

<a name="see-also"></a>Se även
--------

[Leverantörssamarbete](collaborate-vendors-vendor-portal.md)




