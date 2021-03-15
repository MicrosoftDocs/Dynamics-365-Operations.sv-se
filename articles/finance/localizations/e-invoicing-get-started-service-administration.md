---
title: Kom i gång med tjänsteadministreringen för tillägget Elektronisk fakturering
description: I det här avsnittet beskrivs hur du kommer igång med tillägget Elektronisk fakturering.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 111ec65aa826795125d4a9ce835f72e1a0f41b7b
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104438"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a>Kom i gång med tjänsteadministreringen för tillägget Elektronisk fakturering

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:

- Du måste ha tillgång till ditt Microsoft Dynamics Lifecycle Services-konto (LCS).
- Du måste ha ett LCS-projekt som innehåller version 10.0.13 eller senare av Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management. Dessa program måste dessutom distribueras i något av följande Azure-områden:

    - Östra USA
    - Västra USA
    - Norra EU
    - Västra EU

- Du måste ha tillgång till ditt Dynamics 365 Regulatory Configuration Services-konto (RCS).
- Du måste aktivera globaliseringsfunktionen för ditt RCS-konto i funktionshanteringen. Mer information finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md).
- Du måste skapa ett nyckelvalv och ett lagringskonto i Azure. Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a>Installera tillägget för mikrotjänster i Lifecycle Services

1. Logga in på LCS-kontot.
2. Välj panelen **Hantera förhandsgranskning**.
3. I avsnittet **Funktioner i allmänt tillgänglig förhandsversion** väljer du **Tjänst för e-fakturering**.
4. Se till att alternativet **Förhandsgranskning aktiverad** är inställt på **Ja**.

## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a>Ställ in parametrarna för RCS-integrationen med tillägget Elektronisk fakturering

1. Logga in på RCS-kontot.
2. I arbetsytan **elektronisk rapportering** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.
3. På fliken **Tjänst för e-fakturering**, under fliken **URI för tjänstens slutpunkt** anger du ungefärlig tjänsteslutpunkt för ditt Azure-område enligt följande tabell.

    | Azure-område för datacenter | URI för tjänstslutpunkt                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Östra USA                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Västra USA                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Norra EU                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Västra EU                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. Kontrollera att fältet **Program-ID** är inställt på **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Det här värdet är ett fast värde.
5. I fältet **ID för LCS-miljö** anger du ID för ditt LCS-abonnemangskonto.
6. Markera **Spara** och stäng sedan sidan.

## <a name="create-key-vault-secret"></a>Skapa nyckelvalvshemlighet

1. Logga in på RCS-kontot.
2. I arbetsytan **Globaliseringsfunktioner** i avsnittet **Miljö** väljer du panelen **e-fakturering**.
3. På sidan **Miljökonfigurationer** väljer du i åtgärdsfönstret **Tjänstemiljö** och sedan **Parametrar för nyckelval**.
4. Välj **Ny** för att skapa en nyckelvalvshemlighet.
5. I fältet **Namn** anger du namnet för nyckelvalvshemligheten. Ange en beskrivning i fältet **beskrivning**.
6. I fältet **URI för nyckelvalv** klistrar du in hemligheten från Azure Key Vault.
7. Välj **Spara**.

## <a name="create-storage-account-secret"></a>Skapa hemlighet för lagringskonto

1. På sidan **Parametrar för nyckelvalv**, i avsnittet **Certifikat**, väljer du **Lägg till**.
2. I fältet **Namn** anger du namnet för lagringskontots hemlighet. Ange en beskrivning i fältet **beskrivning**.
3. I fältet **Typ** väljer du **Certifikat**.
4. Markera **Spara** och stäng sedan sidan.

## <a name="create-an-electronic-invoicing-add-on-environment"></a>Skapa en miljö för Elektronisk fakturering

1. Logga in på RCS-kontot.
2. I arbetsytan **Globaliseringsfunktioner** i avsnittet **Miljö** väljer du panelen **e-fakturering**.

## <a name="create-a-service-environment"></a>Skapa en tjänstemiljö

1. På sidan **Miljökonfigurationer** väljer du **Tjänstemiljö** i åtgärdsfönstret.
2. Välj **Ny** för att skapa en ny tjänstemiljö.
3. I fältet **Namn** anger du namnet på miljön för e-fakturering. Ange en beskrivning i fältet **beskrivning**.
4. I fältet **Lagringshemlighet för SAS-token** väljer du namnet på det certifikat som måste användas för att ge åtkomst till lagringskontot.
5. I avsnittet **Användare** väljer du **Lägg till** om du vill lägga till en användare som är behörig att skicka in elektroniska fakturor via miljön samt även ansluta till lagringskontot.
6. I fältet **Användar-ID** anger du användarens alias. I fältet **E-postadress** anger du användarens e-postadress.
7. Välj **Spara**.
8. Om dina lands-/regionspecifika fakturor kräver en certifikatkedja för att kunna tillämpa digitala signaturer, väljer du **Parametrar för nyckelvalv** och sedan **Certifikatkedja** i åtgärdsfönstret och följer sedan dessa steg:

    1. Välj **Ny** för att skapa en certifikatkedja.
    2. I fältet **Namn** anger du namnet på certifikatkedjan. Ange en beskrivning i fältet **beskrivning**.
    3. I avsnittet **Certifikat** väljer du **Lägg till** för att lägga till ett certifikat i kedjan.
    4. Använd knappen **Upp** eller **Ner** för att byta certifikatets position i kedjan.
    5. Markera **Spara** och stäng sedan sidan.
    6. Stäng sidan.
9. I åtgärdsfönstret på sidan **Tjänstemiljö** väljer du **Publicera** om du vill publicera miljön i molnet. Värdet i fältet **Status** ändras till **Publicerad**.

## <a name="create-a-connected-application"></a>Skapa ett anslutet program.

1. På sidan **Miljökonfigurationer** väljer du **Anslutna program** i åtgärdsfönstret.
2. Skapa ett anslutet program genom att välja **Ny**.
3. I fältet **Namn** anger du namnet på det program du vill ansluta.
4. I fältet **Program** anger du URL:en för den Finance- och Supply Chain Management-miljö du vill ansluta.
4. I fältet **Klientorganisation** anger du klientorganisationen för Finance and Supply Chain Management-miljön.
5. Välj **Spara**.
6. I åtgärdsfönstret väljer du **Kontrollera anslutning** om du vill testa anslutningen till miljön. Stäng sedan sidan.

## <a name="link-connected-applications-to-environments"></a>Koppla anslutna program till miljöer

1. På sidan **Miljökonfigurationer** väljer du **Ny** om du vill tilldela ett anslutet program till en miljö.
2. I fältet **Anslutet program** väljer du ett anslutet program.
3. I fältet **Tjänstemiljö** väljer du en tjänstemiljö.
4. Markera **Spara** och stäng sedan sidan.

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a>Ställa in integrering av tillägget Elektronisk fakturering i Finance och Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Aktivera integrationsfunktionen för tillägget Elektronisk fakturering

1. Logga in på din instans för Finance eller Supply Chain Management.
2. I arbetsytan **Funktionshantering** söker du efter den nya funktionen **Integrering av tillägg för elektronisk fakturering**. Om den här funktionen inte visas på sidan väljer du **Sök efter uppdateringar**.
3. Välj funktionen och välj sedan **aktivera nu**.

### <a name="set-up-the-service-endpoint-url"></a>Ställ in URL för tjänstslutpunkt

1. Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.
2. På fliken **Överföringstjänst**, i fältet **URL för tjänsteslutpunkt** anger du relevant tjänsteslutpunkt för ditt Azure-område enligt följande tabell.

    | Azure-område för datacenter | URL för tjänstslutpunkt                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Östra USA                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Västra USA                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Norra EU                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Västra EU                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. I fältet **Miljö** anger du namnet på miljön för tillägget Elektronisk fakturering.
4. Markera **Spara** och stäng sedan sidan.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]