---
title: Ställ in mobil arbetsyta för Tillgångshantering
description: I denna artikel beskrivs hur du konfigurerar Microsoft Dynamics 365 Supply Chain Management och mobilappen för ekonomi och drift (Dynamics 365) för att köra den mobila arbetsytan Tillgångshantering som arbetstagare kan använda för att utföra uppgifter inom tillgångshantering.
author: johanhoffmann
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ef4e6bf2ae59adb05c7d4aacc3f5675a5adcafc9
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070066"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a>Ställ in mobil arbetsyta för Tillgångshantering

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar Microsoft Dynamics 365 Supply Chain Management och mobilappen Ekonomi och drift (Dynamics 365) för att köra den mobila arbetsytan **Tillgångshantering** som arbetstagare kan använda för att utföra uppgifter inom tillgångshantering.

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a>Ställ in användare av underhållsarbetare i Supply Chain Management

För varje användare som kräver åtkomst till den mobila arbetsytan för **Hantering av tillgångar** följer du dessa steg.

1. I Supply Chain Management, gå till **Personal \> Arbetare** och se till att det finns en arbetarpost för den användare som du vill konfigurera. Skapa en ny arbetarpost som krävs.
1. Gå till **Tillgångshantering \> Inställningar \> Arbetare \> Arbetare**, och se till att den arbetarpost som du identifierade (eller skapade) i föregående steg är mappad till en underhållspost. Skapa en ny underhållsarbetarepost som obligatorisk, och ange fältet **Arbetare** till arbetarposten från föregående steg.
1. Gå till **Tillgångshantering \> Inställningar \> Arbetare \> underhållsarbetargrupper**, och se till att den underhållsarbetargrupper som du identifierade (eller skapade) i föregående steg är mappad till en underhållspost.
1. Gå till **Systemadministration \> Användare**.
1. Välj relevant användare i rutnätet.
1. På snabbfliken **Användardetaljer** anger du fältet **Person** till arbetarkontot som du vill associera med det aktuella användarkontot. Det här arbetarkontot ska vara arbetarposten som du identifierade (eller skapade) i steg 1 och mappas till en underhållsarbetarepost i steg 2.

> [!NOTE]
> Användarbehörigheter och säkerhetsroller gäller funktionerna i den mobila arbetsytan för **hantering av tillgångar** på samma sätt som de gäller funktionerna i användargränssnittet för Supply Chain Management. Därför måste varje användare som du konfigurerar för att få åtkomst till den mobila arbetsytan för **hantering av tillgångar** ha de säkerhetsroller som krävs för att utföra liknande åtgärder direkt i Supply Chain Management.

## <a name="publish-the-asset-management-mobile-workspace"></a>Publicera mobil arbetsyta för Tillgångshantering

Om du vill göra funktioner för tillgångshantering tillgängliga i mobilappen för ekonomi och drift (Dynamics 365) måste du publicera den mobila arbetsytan **Tillgångshantering**.

1. I Supply Chain Management väljer du knappen **Inställningar** (kugghjulssymbolen i det övre högra hörnet) och väljer sedan **Mobilapp** på menyn.
1. I dialogrutan **hantera mobilapp** hitta panelen **Hantera tillgång**. Om den innehåller texten "I metadata – inte publicerats" har arbetsytan ännu inte publicerats. Om den innehåller texten "I metadata – publicerat" har arbetsytan redan publicerats och du kan hoppa över resten av den här proceduren.

    ![Dialogrutan Hantera mobilapp.](media/mobile-workspaces.png "Dialogrutan Hantera mobilapp")

1. Välj panelen för **Tillgångshantering** och välj sedan **Publicera** i verktygsfältet. Efter några sekunder bör du få ett meddelande som anger att arbetsytan har publicerats utan resultat. Dessutom ska texten på panelen ändras till "I metadata – publicerat".

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a>Installera och konfigurera mobilappen för ekonomi och drift (Dynamics 365)

1. Gå till någon av följande appbutiker för att installera appen **Microsoft Ekonomi och drift (Dynamics 365)** på din mobila enhet:

    - [För Google Android enheter](https://go.microsoft.com/fwlink/?linkid=850662)
    - [För Apple iOS-enheter](https://go.microsoft.com/fwlink/?linkid=850663)

1. Öppna appen för ekonomi och drift (Dynamics 365). Inloggningssidan ska visas. I fältet **Logga in** ange Supply Chain Management URL, eller välj senaste URL i listan **senaste miljöer** och tryck **anslut**.

    ![Inloggningssida.](media/mobile-app-sign-in.png "Inloggningssida")

1. Om du uppmanas att bekräfta anslutningen markerar du kryssrutan **Jag förstår** och trycker sedan på **Anslut**.
1. På sidan **Välj ett konto** använder du ditt Microsoft-konto för att logga in på mobilprogrammet.

    Sidan **arbetsytor** visas. Den listar varje mobil arbetsyta som har publicerats av din Supply Chain Management-instans.

    ![Lista över arbetsytor.](media/mobile-app-workspaces.png "Lista över arbetsytor")

1. Om du måste ändra den juridiska personen (företaget) trycker du på menyknappen (kallas ibland hamburgaren eller hamburgerknappen) i det övre vänstra hörnet och sedan på **Ändra företag**.

    ![Ändra den juridiska personen.](media/mobile-app-change-comp.png "Ändra den juridiska personen.")

1. På sidan **Arbetsytor** väljer du den arbetsyta som du vill arbeta med för att öppna den.

    ![Mobil arbetsyta för Tillgångshantering.](media/mobile-app-asset-workspace.png "Mobil arbetsyta för Tillgångshantering")

## <a name="work-with-the-asset-management-mobile-workspace"></a>Arbeta med mobil arbetsyta för Tillgångshantering

Mer information om hur du arbetar med den mobila arbetsytan **Tillgångshantering** finns i [Använda den mobila arbetsytan för Tillgångshantering](asset-management-mobile-workspace.md).

Mer information om mobilappen för ekonomi och drift (Dynamics 365) finns i [Startsida för mobilapp](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
