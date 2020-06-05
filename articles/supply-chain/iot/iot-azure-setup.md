---
title: Konfigurera Azure-resurser för IoT-information
description: I det här avsnittet beskrivs hur du skapar och konfigurerar de Microsoft Azure-resurser som krävs för IoT-information.
author: robinarh
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1f05f597f86df602c0e00af006b7ccf804f50929
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386563"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a>Konfigurera Azure-resurser för IoT-information

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du skapar och konfigurerar de Microsoft Azure-resurser som krävs för IoT-information.

## <a name="create-azure-resources"></a>Skapa Azure-resurser

Följ stegen nedan om du vill skapa ett IoT-nav en Redis-cache och ett nyckelvalv som Microsoft Dynamics 365 Supply Chain Management kan få åtkomst till.

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a>Kontrollera att förstaparts app-ID för Microsoft Dynamics ERP Microservices finns i din klientorganisation

Du kan kontrollera att förstaparts app-ID för Microsoft Dynamics ERP Microservices finns i din klientorganisation genom att följa stegen nedan.

1. Logga in på Azure portal på <https://portal.azure.com>.
2. Gå till **Azure Active Directory**.
3. Gå till **Företagsprogram**.
4. I fältet **Programtyp** väljer du **Microsoft-program**.
5. I sökfältet anger du **Microsoft Dynamics ERP Microservices**.
6. Kontrollera att **Microsoft Dynamics ERP Microservices** finns i listan. Andra program har liknande namn. Se därför till att du använder rätt program. App-ID:t är **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Om programmet inte finns med i listan måste du lägga till det i klientorganisationen:

    1. I Azure-portalen väljer du knappen för att öppna Azure Cloud Shell i verktygsfältet.
    2. Kör kommandot **Install-Module AzureAD**. Ange **J** om du vill installera modulen.
    3. Kör kommandot **Get-InstalledModule -Name "AzureAD"** för att bekräfta att modulen har installerats.
    4. Kör kommandot **Connect-AzureAD -Confirm** för att köra autentiseringen.
    5. Kör kommandot **New-AzureADServicePrincipal-AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Du kan nu upprepa steg 1 till och med 6 och kontrollera att app-ID:t finns i din klientorganisation.

### <a name="create-a-key-vault-resource"></a>Skapa en nyckelvalvresurs

Gör så här om du vill skapa en nyckelvalvsresurs.

1. Skapa eller gå till en resursgrupp i Azure-portalen.
2. Markera **Lägg till**.
3. På sidan **Ny** anger du **Nyckelvalv** i sökrutan. Markera sedan **Skapa**.
4. På sidan **Skapa nyckelvalv** anger du ett värde i fältet **Namn på nyckelvalv**.
5. Granska standardvärdena och välj sedan **Granska + skapa**.
6. Markera **Skapa**.

Nyckelvärdet skapas i bakgrunden.

### <a name="create-an-iot-hub-resource"></a>Skapa en IoT-navresurs

Gör så här om du vill skapa en IoT-navresurs.

1. Skapa eller gå till en resursgrupp.
2. Markera **Lägg till**.
3. På sidan **Ny** anger du **Iot-nav** i sökrutan. Markera sedan **Skapa**.
4. I fältet **IoT-navnamn** anger du ett namn.
5. Granska standardvärdena och välj sedan **Granska + skapa**.
6. Markera **Skapa**.

IoT-navet skapas i bakgrunden.

> [!NOTE]
> Vi rekommenderar att du endast skapar en enda IoT-navresurs per miljö.

### <a name="create-a-redis-cache-resource"></a>Skapa en resurs för Redis-cache

Gör så här om du vill skapa en Redis-cacheresurs.

1. Skapa eller gå till en resursgrupp.
2. Markera **Lägg till**.
3. På sidan **Ny** anger du **Azure Cache for Redis** i sökfältet. Markera sedan **Skapa**.
4. I fältet **DNS-namn** anger du ett namn.
5. Granska standardvärdena och välj sedan **Skapa**.

Redis-cachen skapas i bakgrunden.

> [!NOTE]
> Vi rekommenderar att du endast skapar en enda Redis-cache per miljö.

Alla resurser har nu skapats.

## <a name="configure-the-azure-resources"></a>Konfigurera Azure-resurserna

### <a name="configure-the-iot-hub"></a>Konfigurera IoT-navet

Följ dessa steg för att konfigurera IoT-navet:

1. Markera IoT Hub-resursen bland dina resurser.
2. I det vänstra navigeringsfönstret väljer du **Inbyggda slutpunkter**.
3. Under **Konsumentgrupper** klistrar du in följande konsumentgrupper. Dessa konsumentgrupper motsvarar de färdiga scenarierna.

    + microsoft.dynamics.iotintelligence-1
    + microsoft.dynamics.iotintelligence-2
    + microsoft.dynamics.iotintelligence-3

### <a name="configure-the-key-vault"></a>Konfigurera nyckelvalvet

Följ dessa steg när du vill konfigurera nyckelvalvet.

1. Markera nyckelvalvsresursen bland dina resurser.
2. I det vänstra navigeringsfönstret välj er du **Policyåtkomst**.
3. Välj **Lägg till en åtkomstpolicy**.
4. På sidan **Lägg till åtkomstpolicy**, i fältet **Hemliga behörigheter**, väljer du **Hämta** och **Lista**.
5. Klicka på i **Välj primär**.
6. I dialogrutan **Primär** letar du upp och väljer **Microsoft Dynamics ERP Microservices**. Välj sedan **Välj**.
7. Markera **Lägg till**.
8. Välj **Spara**.

Appen har nu åtkomst till hemligheterna i nyckelvalvet.

### <a name="save-the-iot-hub-connection-string-secret"></a>Spara hemligheten för IoT-navets anslutningssträng

Gör så här om du vill spara hemligheten för IoT-navets anslutningssträng:

1. Markera IoT Hub-resursen bland dina resurser.
2. I det vänstra navigeringsfönstret väljer du **Inbyggda slutpunkter**.
3. Kopiera värdet i fältet för **Händelsenavskompatilbel slutpunkt**.
4. Gå till nyckelvalvsresursen.
5. I navigeringsfönstret till vänster välj er du **Hemligheter**.
6. Välj **Generera/Importera**.
7. Ange sedan ett namn i fältet **Namn**.
8. I fältet **Värde** klistrar du in det slutpunktsvärde som du tidigare kopierade.
9. Markera **Skapa**.

### <a name="save-the-redis-cache-connection-string-secret"></a>Spara hemligheten för Redis-cachens anslutningssträng

Gör så här om du vill spara hemligheten för Redis-cachens anslutningssträng:

1. Markera Redis-cache-resursen bland dina resurser.
2. Välj **Åtkomstnycklar**.
3. Kopiera värdet i fältet **Primär anslutningssträng**.
4. Gå till nyckelvalvsresursen.
5. I navigeringsfönstret till vänster välj er du **Hemligheter**.
6. Välj **Generera/Importera**.
7. Ange sedan ett namn i fältet **Namn**.
8. I fältet **Värde** klistrar du in den anslutningssträng som du tidigare kopierade.
9. Markera **Skapa**.

> [!NOTE]
> När du uppdaterar en av anslutningssträngarna måste du också uppdatera de hemliga värdena.

Du har nu slutfört etableringen av de nödvändiga Azure-resurserna. Nästa steg är att [installera IoT-information-tillägget i Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).
