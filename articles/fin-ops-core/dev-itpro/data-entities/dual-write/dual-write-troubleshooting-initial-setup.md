---
title: Felsöka problem under första installationen
description: Ämnet innehåller information som kan hjälpa dig att åtgärda problem som kan uppstå under den första installationen av integrering av dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 7c51a92ab101937a0ccf630fa0355485e42e9a0deca36c23327d96976f5228b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758202"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Felsöka problem under första installationen

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse. Särskilt innehåller det information som kan hjälpa dig att åtgärda problem som kan uppstå under den första installationen av integrering av dubbelriktad skrivning.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Du kan inte länka en Finance and Operations-app till Dataverse

**Obligatoriska autentiseringsuppgifter för att konfigurera dubbelriktad skrivning:** Systemadministratören i Finance and Operations-appar och Dataverse.

Fel på sidan **Konfigurera länk till Dataverse** orsakas vanligtvis av ofullständiga installations- eller behörighetsproblem. Kontrollera att hela hälsokontrollen passerar **Konfigurera länk till Dataverse** som visas i följande illustration. Du kan inte länka dubbelriktad skrivning om inte hela hälsokontrollen passerar.

![Lyckad hälsokontroll.](media/health_check.png)

Du måste ha Azure AD autentiseringsuppgifter för klientadministratör för att länka Finance and Operations och Dataverse-miljöer. När du har länkat miljöerna kan användare logga in med hjälp av sina kontouppgifter och uppdatera en befintlig tabellmappning.

## <a name="error-when-you-open-the-link-to-dataverse-page"></a>Fel när du öppnar sidan länka till Dataverse

**Nödvändiga autentiseringsuppgifter för att åtgärda problemet:** Azure AD klientadministratör

Du kan få följande felmeddelande när du öppnar sidan **Länka till Dataverse** i en Finance and Operations-app:

*Svarsstatuskoden anger inte lyckad: 404 (hittades inte).*

Det här felet uppstår när medgivandesteget inte har slutförts. För att bekräfta om godkännandesteget är slutfört, logga in på portal.Azure.com med hjälp av Azure AD klientadministratörskontot och se om tredje partens app som har ID **33976c19-1db5-4c02-810e-c243db79efde** visas i listan Azure AD **företagsappar**. Om den inte gör det måste du ge appmedgivande.

Följ dessa steg för att ge appen samtycke.

1. Öppna följande URL med hjälp av administratörsuppgifterna. Du bör uppmanas att ge samtycke.

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. Välj **Acceptera** för att ange att du ger ditt samtycke till att installera appen som har ID **33976c19-1db5-4c02-810e-c243db79efde** i din klientorganisation.

    > [!TIP]
    > Den här appen krävs för att länka Dataverse och Finance and Operations-appar. Om du har problem med det här steget öppnar du webbläsaren i inkognitoläge (i Google Chrome) eller InPrivate-läge (i Microsoft Edge).

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a>Kontrollera att företagsdata och team med dubbelriktad skrivning är korrekt konfigurerade när du länkar

För att säkerställa att dubbelriktad skrivning fungerar korrekt skapas de företag som du väljer under konfigurationen i Dataverse-miljön. Som standard är dessa företag skrivskyddade och egenskapen **IsDualWriteEnable** är inställd på **Sant**. Dessutom skapas standardägaren och teamet för den ägande affärsenheten och teamet och inkluderar företagsnamnet. Innan du aktiverar kartorna kontrollerar du att standardteamets ägare har angetts. För att hitta tabellen **företag (CDM\_företag)** följer du stegen nedan.

1. Välj filtret i det övre högra hörnet i programmet för kundengagemangsappen.
2. Välj **Företag** i listrutan.
3. Välj **Kör** om du vill visa resultatet.
4. Välj det företag som länkades när du konfigurerade dubbelskrivning.
5. Kontrollera att kolumnen **standardägargrupp** har ett värde. I bilden nedan är kolumnen **standardägargrupp** anges till **USMF dubbelriktad skrivning**.

    ![Verifiera standardägargruppen.](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Hitta gränsen för antal juridiska tabeller eller företag som kan länkas för dubbelriktad skrivning

Följande felmeddelande kan visas när du försöker att aktivera kartor:

*Del i dubbelriktad skrivning - registrering av plugin-program misslyckades: \[(Det gick inte att skaffa karta över partitioner för projekt-DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Felet överskrider högsta antal tillåtna partitioner för mappning av DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], ett eller flera fel uppstod.*

Den aktuella gränsen när du länkar miljöer är ungefär 40 juridiska tabeller. Det här felet uppstår om du försöker aktivera mappningar och mer än 40 juridiska tabeller är länkade mellan miljöer.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]