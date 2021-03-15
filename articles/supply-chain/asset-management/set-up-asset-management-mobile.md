---
title: Ställ in mobil arbetsyta för tillgångshantering
description: I det här avsnittet beskrivs hur du ställer in Microsoft Dynamics 365 Supply Chain Management och Finance and Operations (Dynamics 365) mobilappen för att köra en tillgångshantering mobil arbetsyta som arbetstagare kan använda för att utföra uppgifter för hantering av tillgångar.
author: johanhoffmann
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9c2410c50b5d289792e2cc364674e1e093653590
ms.sourcegitcommit: 995c678b4715be267f1f97148902a6b3dde3bcab
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/20/2021
ms.locfileid: "5033231"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a>Ställ in mobil arbetsyta för tillgångshantering

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in Microsoft Dynamics 365 Supply Chain Management och Finance and Operations (Dynamics 365) mobilapp för att köra en **Tillgångshantering** mobil arbetsyta som arbetstagare kan använda för att utföra uppgifter för hantering av tillgångar.

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a>Ställ in användare av underhållsarbetare i Supply Chain Management

För varje användare som kräver åtkomst till den mobila arbetsytan för **Hantering av tillgångar** följer du dessa steg.

1. I Supply Chain Management, gå till **Personal \> Arbetare** och se till att det finns en arbetarpost för den användare som du vill ställa in. Skapa en ny arbetarpost som krävs.
1. Gå till **Tillgångshantering \> Inställningar \> Arbetare \> Arbetare**, och se till att den arbetarpost som du identifierade (eller skapade) i föregående steg är mappad till en underhållspost. Skapa en ny underhållsarbetarepost som obligatorisk, och ange fältet **Arbetare** till arbetarposten från föregående steg.
1. Gå till **Tillgångshantering \> Inställningar \> Arbetare \> underhållsarbetargrupper**, och se till att den underhållsarbetargrupper som du identifierade (eller skapade) i föregående steg är mappad till en underhållspost.
1. Gå till **Systemadministration \> Användare**.
1. Välj relevant användare i rutnätet.
1. På snabbfliken **Användardetaljer** anger du fältet **Person** till arbetarkontot som du vill associera med det aktuella användarkontot. Det här arbetarkontot ska vara arbetarposten som du identifierade (eller skapade) i steg 1 och mappas till en underhållsarbetarepost i steg 2.

> [!NOTE]
> Användarbehörigheter och säkerhetsroller gäller funktionerna i den mobila arbetsytan för **hantering av tillgångar** på samma sätt som de gäller funktionerna i användargränssnittet för Supply Chain Management. Därför måste varje användare som du ställer in för att få åtkomst till den mobila arbetsytan för **hantering av tillgångar** ha de säkerhetsroller som krävs för att utföra liknande åtgärder direkt i Supply Chain Management.

## <a name="publish-the-asset-management-mobile-workspace"></a>Publicera mobil arbetsyta för tillgångshantering

Om du vill göra tillgångshanteringsfunktioner tillgängliga i Finance and Operations (Dynamics 365) mobilapp, måste du publicera mobila arbetsytan **tillgångshantering**.

1. I Supply Chain Management väljer du knappen **Inställningar** (kugghjulssymbolen i det övre högra hörnet) och väljer sedan **Mobilapp** på menyn.
1. I dialogrutan **hantera mobilapp** hitta panelen **Hantera tillgång**. Om den innehåller texten "I metadata - inte publicerats" har arbetsytan ännu inte publicerats. Om den innehåller texten "I metadata - publicerat" har arbetsytan redan publicerats och du kan hoppa över resten av den här proceduren.

    ![Dialogrutan Hantera mobilapp](media/mobile-workspaces.png "Dialogrutan Hantera mobilapp")

1. Välj panelen för **tillgångshantering** och välj sedan **Publicera** i verktygsfältet. Efter några sekunder bör du få ett meddelande som anger att arbetsytan har publicerats utan resultat. Dessutom ska texten på panelen ändras till "I metadata - publicerat".

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a>Installera och konfigurera Finance and Operations (Dynamics 365) mobilappen

1. Gå till någon av följande appbutiker för att installera **Microsoft Finance and Operations (Dynamics 365)**-appen på din mobila enhet:

    - [För Google Android enheter](https://go.microsoft.com/fwlink/?linkid=850662)
    - [För Apple iOS-enheter](https://go.microsoft.com/fwlink/?linkid=850663)

1. Öppna Finance and Operations (Dynamics 365) appen. Inloggningssidan ska visas. I fältet **Logga in** ange Supply Chain Management URL, eller välj senaste URL i listan **senaste miljöer** och tryck **anslut**.

    ![Inloggningssida](media/mobile-app-sign-in.png "Inloggningssida")

1. Om du uppmanas att bekräfta anslutningen markerar du kryssrutan **Jag förstår** och trycker sedan på **Anslut**.
1. På sidan **Välj ett konto** använder du ditt Microsoft-konto för att logga in på mobilprogrammet.

    Sidan **arbetsytor** visas. Den listar varje mobil arbetsyta som har publicerats av din Supply Chain Management-instans.

    ![Lista över arbetsytor](media/mobile-app-workspaces.png "Lista över arbetsytor")

1. Om du måste ändra den juridiska personen (företaget) trycker du på menyknappen (kallas ibland hamburgaren eller hamburgerknappen) i det övre vänstra hörnet och sedan på **Ändra företag**.

    ![Ändra den juridiska personen.](media/mobile-app-change-comp.png "Ändra den juridiska personen.")

1. På sidan **Arbetsytor** väljer du den arbetsyta som du vill arbeta med för att öppna den.

    ![Mobil arbetsyta för tillgångshantering](media/mobile-app-asset-workspace.png "Mobil arbetsyta för tillgångshantering")

## <a name="work-with-the-asset-management-mobile-workspace"></a>Arbeta med mobil arbetsyta för tillgångshantering

Mer information om hur du arbetar med den mobila arbetsytan **tillgångshantering** finns i [Använda den mobila arbetsytan för tillgångshantering](asset-management-mobile-workspace.md).

Mer information om Finance and Operations (Dynamics 365) mobilappen finns på [startsidan för Mobilappen](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]