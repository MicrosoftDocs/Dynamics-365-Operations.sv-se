---
title: Kom i gång med tjänstadministration för elektronisk fakturering
description: I det här avsnittet beskrivs hur du kommer igång med Elektronisk fakturering.
author: gionoder
ms.date: 05/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: feb8160cd920906765f7ef4a393e15c2be5d8c2cd60c3646e15648980ff27a06
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765654"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a>Kom i gång med tjänstadministration för elektronisk fakturering

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:

- Du måste ha tillgång till ditt Microsoft Dynamics Lifecycle Services-konto (LCS).
- Du måste ha ett LCS-projekt som innehåller version 10.0.17 eller senare av Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management. Dessa program måste dessutom distribueras i något av följande Azure-områden:

    - USA
    - Europa
    - Storbritannien
    - Asien

- Du måste ha tillgång till ditt Dynamics 365 Regulatory Configuration Services-konto (RCS).
- Du måste aktivera globaliseringsfunktionen för ditt RCS-konto i funktionshanteringen. Mer information finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md).
- Du måste skapa ett nyckelvalv och ett lagringskonto i Azure. Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Installera tillägget för mikrotjänster i Lifecycle Services

1. Logga in på ditt LCS-konto och LCS-projektinstrumentpanelen, LCS-projekt.
2. Välj ditt distributionsprojekt i projektet på LCS-miljöinstrumentpanelen. Det projekt du väljer måste köras.
3. Under fliken **Power Platform-integrering**, i fältgruppen **Miljötillägg**, väljer du **Installera ett nytt tillägg**.
4. Välj **Elektronisk fakturering**.
5. I fältet **AAD-program-ID**, ange **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Detta är ett fast värde.
6. I fältet **AAD innehavar-ID** anger du innehavar-ID för ditt Azure abonnemangskonto.
7. Granska villkoren och markera sedan kryssrutan.
8. Välj **Installera**.


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Ställ in parametrarna för RCS-integrationen med Elektronisk fakturering

1. Logga in på RCS-kontot.
2. I arbetsytan **elektronisk rapportering** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.
3. På fliken **Tjänst för e-fakturering**, under fliken **URI för tjänstens slutpunkt** anger du ungefärlig tjänsteslutpunkt för ditt Azure-område enligt följande tabell.

    | Azure-område för datacenter | URI för tjänstslutpunkt                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | USA              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Storbritannien             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asien                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

4. Kontrollera att fältet **Program-ID** är inställt på **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Det här värdet är ett fast värde.
5. I fältet **ID för LCS-miljö** anger du ID för ditt LCS-miljö.
6. Markera **Spara** och stäng sedan sidan.

## <a name="create-key-vault-references"></a>Skapa en nyckelvalvsreferens

1. Logga in på RCS-kontot.
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Miljöer**, välj panelen **Elektroniska fakturor**.
3. På sidan **Miljökonfigurationer** väljer du i åtgärdsfönstret **Tjänstemiljö** och sedan **Parametrar för nyckelval**.
4. Välj **Ny** för att skapa en nyckelvalvsreferens.
5. I fältet **Namn** anger du namnet för nyckelvalvsreferens. Ange en beskrivning i fältet **beskrivning**.
6. I fältet **URI för nyckelvalv** klistrar du in nyckelvalvshemlighet från Azure Key Vault. Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).
7. Välj **Spara**.

## <a name="create-storage-account-secret"></a>Skapa hemlighet för lagringskonto

1. På sidan **Miljökonfigurationer** väljer du i åtgärdsfönstret **Tjänstemiljö** > **Parametrar för nyckelval**.
2. Välj en **Nyckelvalvsreferens** och i avsnittet **Certifikat**, välj **Lägg till**.
3. I fältet **Namn** anger du namnet för lagringskontots hemlighet. Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).
4. Ange en beskrivning i fältet **beskrivning**.
5. Välj **Typ** i fältet **Hemlighet**.
6. Markera **Spara** och stäng sedan sidan.

## <a name="create-a-digital-certificate-secret"></a>Skapa en hemlighet för digitalt certifikat

1. På sidan **Miljökonfigurationer** väljer du i åtgärdsfönstret **Tjänstemiljö** och sedan **Parametrar för nyckelval**.
2. Välj en **Nyckelvalvsreferens** och i avsnittet **Certifikat**, välj **Lägg till**.
3. I fältet **Namn** anger du namnet för hemlighet för digitalt certifikat. Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).
4. Ange en beskrivning i fältet **beskrivning**.
5. I fältet **Typ** väljer du **Certifikat**.
6. Markera **Spara** och stäng sedan sidan.

## <a name="create-a-service-environment"></a>Skapa en tjänstemiljö

1. Logga in på RCS-kontot.
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Miljöer**, välj panelen **Elektroniska fakturor**.
3. På sidan **Miljökonfigurationer** väljer du **Tjänstemiljö** i åtgärdsfönstret.
4. Välj **Ny** för att skapa en ny tjänstemiljö.
5. I fältet **Namn** anger du namnet på miljön för e-fakturering. Ange en beskrivning i fältet **beskrivning**.
6. I fältet **Lagringshemlighet för SAS-token** väljer du namnet på lagringskontots hemlighet som måste användas för att ge åtkomst till lagringskontot.
7. I avsnittet **Användare** väljer du **Lägg till** om du vill lägga till en användare som är behörig att skicka in elektroniska fakturor via miljön samt även ansluta till lagringskontot.
8. I fältet **Användar-ID** anger du användarens alias. I fältet **E-postadress** anger du användarens e-postadress.
9. Välj **Spara**.
10. Om dina lands-/regionspecifika fakturor kräver en certifikatkedja för att kunna tillämpa digitala signaturer, väljer du **Parametrar för nyckelvalv** och sedan **Certifikatkedja** i åtgärdsfönstret och följer sedan dessa steg:
    1. Välj **Ny** för att skapa en certifikatkedja.
    2. I fältet **Namn** anger du namnet på certifikatkedjan. Ange en beskrivning i fältet **beskrivning**.
    3. I avsnittet **Certifikat** väljer du **Lägg till** för att lägga till ett certifikat i kedjan.
    4. Använd knappen **Upp** eller **Ner** för att byta certifikatets position i kedjan.
    5. Markera **Spara** och stäng sedan sidan.
    6. Stäng sidan.
11. I åtgärdsfönstret på sidan **Tjänstemiljö** väljer du **Publicera** om du vill publicera miljön i molnet. Värdet i fältet **Status** ändras till **Publicerad**.

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

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a>Ställa in integrering av elektronisk fakturering i Finance och Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a>Aktivera integrationsfunktionen för Elektronisk fakturering

1. Logga in på din instans för Finance eller Supply Chain Management.
2. I arbetsytan **Funktionshantering** söker du efter den nya funktionen **Integrering av för elektronisk fakturering**. Om den här funktionen inte visas på sidan väljer du **Sök efter uppdateringar**.
3. Välj funktionen och välj sedan **aktivera nu**.

### <a name="set-up-the-service-endpoint-url"></a>Ställ in URL för tjänstslutpunkt

1. Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.
2. På fliken **Överföringstjänst**, i fältet **URL för tjänsteslutpunkt** anger du relevant tjänsteslutpunkt för ditt Azure-område enligt följande tabell.

    | Azure-område för datacenter | URI för tjänstslutpunkt                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | USA              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Storbritannien             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asien                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. I fältet **Miljö** anger du namnet på miljön för tjänstemiljö publicerad i Elektronisk fakturering.
4. Markera **Spara** och stäng sedan sidan.

### <a name="enable-flighting-keys"></a>Aktivera flygnycklar

Aktivera flygnycklar för Microsoft Dynamics 365 Finance eller Microsoft Dynamics 365 Supply Chain Management-versioner 10.0.17 eller tidigare. 
1. Kör följande SQL-kommando:

    INFOGA I SYSFLIGHTING (FLIGHTNAME, ENABLED) VÄRDEN ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    INFOGA I SYSFLIGHTING (FLIGHTNAME, ENABLED) VÄRDEN ('ElectronicInvoicingServiceIntegrationFeature', 1)

2. Utför ett IISreset-kommando för alla AOS:er.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
