---
title: Konfigurera en arbetare med den mobila jobbenheten
description: I denna arikel visas hur du tilldelar de korrekta rollerna till användarkontot för en arbetare och sedan aktiverar arbetaren för att utföra butiksregistreringar.
author: johanhoffmann
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f6f51a66d49cafd172ba123bf883fb41cdcb5c3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844344"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Konfigurera en arbetare med den mobila jobbenheten

[!include [banner](../../includes/banner.md)]

I denna arikel visas hur du tilldelar de korrekta rollerna till användarkontot för en arbetare och sedan aktiverar arbetaren för att utföra butiksregistreringar.

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a>Kontrollera att en arbetstagare har tilldelats en viss roll

I det här exemplet kontrollerar du att användaren "SHANNON" har tilldelats rollen maskinoperatör innan du konfigurerar arbetarkontot.

1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Användare > Användare**.
2. Sök efter en användare i snabbfiltret. Ange `shannon` i det här exemplet.
3. Markera länken i kolumnen **användar-ID** för det användarkonto som visas.
4. I trädet **Användares roller** väljer du **Roller > Maskinoperatör**.
5. Stäng sidorna **användarinformation** och **användare** för att gå tillbaka till startsidan.

## <a name="configure-worker-account"></a>Konfigurera arbetarkonto.
1. Gå till **navigeringsfönstret > moduler > personal > arbetare > arbetare**.
2. Sök efter en användare i snabbfiltret. Ange `shannon` i det här exemplet.
3. Markera länken i kolumnen **Namn** för det användarkonto som visas.
4. Välj fliken **tidsregistrering**.
5. Välj **Aktivera på registreringsterminaler**
6. Ange eller välj värden i följande fält:  

    - **Beräkningsgrupp**  
    - **Standardberäkningsgrupp**  
    - **Godkännandegrupp**  
    - **Standardprofil**  
    - **Profilgrupp**  

7. Välj **OK**.
8. Klicka på **Redigera** för att ange ett bricknummer för den nya tidsregistreringsarbetaren. Ange ett värde i fältet **ID-bricka**.
9. Välj **Spara**.
10. Stäng sidorna **arbetardetaljer** och **arbetare**.

## <a name="assign-worker-to-device-group"></a>Tilldela arbetare till enhetsgrupp.
1. Gå till **Produktionskontroll > Inställningar > Tillverkningskörning > Konfigurera jobbkort för enheter**.
2. Markera **Lägg till**.
3. Välj önskad arbetare i listan. Välj **SHANNON** i det här exemplet.
4. Välj **OK**.
5. Välj **Redigera**.
6. I fältet **Produktionsenhet** kan du konfigurera standardfiltret för arbetaren. Då säkerställs att endast produktionsjobb för den valda produktionsenheten visas när arbetaren loggar in på enheten. Ange önskat värde.
7. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]