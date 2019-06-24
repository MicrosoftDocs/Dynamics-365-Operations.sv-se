---
title: Publicera jobb på externa karriärwebbplatser från Attract
description: Det här avsnittet beskriver hur du använder Dynamics 365 for Talent - Attract att publicera jobb till externa rekryteringswebbplatser
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 9c27d1810a89ed7d7a7745e41c5f118dbdfe5dda
ms.sourcegitcommit: cadce85ca3004d53caf6bc49147a524c1bfd421f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/16/2019
ms.locfileid: "1590492"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a>Publicera jobb på externa karriärwebbplatser från Attract

[!include [banner](../includes/banner.md)]

Du vill få dina lediga befattningar framför så många kvalificerade kandidater som möjligt. Rekryteringswebbplatser som Broadbean hjälper dig att uppnå det här målet. Microsoft Dynamics 365 Talent: Attract låter dig nu publicera jobb på Broadbean och Microsoft tillhandahåller ständigt nya erbjudanden inom detta område.

## <a name="post-jobs-to-broadbean"></a>Publicera jobb på Broadbean

Innan du kan publicera jobb till Broadbean, måste du konfigurera Broadbean-integrationen.

> [!NOTE]
> - Om du vill skicka jobb till externa platser måste du ha [tillägget för omfattande anställning](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - Om du vill bokföra jobb på Broadbean via Attract måste du ha ett Broadbean-abonnemang.
> - Den här funktionen är för närvarande i förhandsgranskning. Om du vill prova den måste du [aktivera den i Attract administrationsinställningar](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="configure-broadbean-integration"></a>Konfigurera Broadbean-integration

1. Logga in på Attract som en administratör.
2. Välj knappen **inställningar** (växelsymbol) i det övre högra hörnet på sidan och välj sedan **administratörscenter**.
3. På fliken **Inställningar av jobbtavla** i avsnittet **Aktivera Broadbean-integration** aktiverar du integrationen.
4. Kontakta Broadbean och skriv sedan in informationen i **Användarnamn, klient-ID, krypteringstoken**.

> [!WARNING]
> Inloggningsinformationen för Broadbean är känslig och konfidentiell. Därför ska den sparas och delas ansvarsfullt. Alla som har en administratörsroll i Attract kan visa denna inloggningsinformation.

> [!NOTE]
> Microsoft och Attract är inte involverade i att skapa och underhålla dessa värden. Det är ditt ansvar att hålla dem uppdaterade i Attract och arbeta med Broadbean för att åtgärda problem som rör dina autentiseringsuppgifter.

### <a name="post-a-job-to-broadbean"></a>Publicera jobb på Broadbean

När Broadbean har aktiverats kan rekryterare och administratörer publicera ett jobb på den. Du måste ha en svars-URL för jobbet.

1. I Attract öppnar du det jobb som du vill publicera i Broadbean.
2. I avsnittet **bokföringar** väljer du knappen **bokför nu** som motsvarar Broadbean.
3. Följ anvisningarna i Broadbean-fönstret.

Attract skickar följande information till Broadbean:

- ID för begäran
- Jobbtitel
- Jobbeskrivning
- Plats för jobbet
- Svars-URL
- Rekryteringsinformation

Efter att Broadbean slutför publiceringen visar avsnittet **Publiceringar** av jobbet i Attract Broadbean status som **publicerad**.

> [!NOTE]
> - Broadbean kräver fältet **bransch**. För närvarande är detta fält som standard inställt på **IT**. Du kan emellertid ändra värdet till rätt branschen i fönstret för Broadbean jobbpublicering.
> - Det tar en stund för Broadbean att slutföra publicering av jobbet till alla jobbtavlor som du har valt. Därför kan finnas det en fördröjning innan Attract ger en statusuppdatering för jobbet.

### <a name="view-a-broadbean-job-posting"></a>Visa en Broadbean jobbpublicering

När du har publicerat ett jobb till Broadbean kan du visa det från Attract.

1. I Attract öppnar du det jobb som du vill visa i Broadbean.
2. I avsnittet **publiceringar** väljer du ellips-knappen (**...**) som motsvarar Broadbean och markerar sedan **visa**.

Broadbean jobbpublicering visas i ett nytt fönster.

### <a name="update-a-broadbean-job-posting"></a>Uppdatera en Broadbean jobbpublicering

Du kan uppdatera en Broadbean jobbpublicering på två sätt.

1. I Attract öppnar du det jobb som du vill uppdatera.
2. I avsnittet **bokföringar** väljer du knappen **uppdatera publicering** som motsvarar Broadbean.
3. Redigera publiceringen i Broadbean-fönstret.

–eller–

1. I Attract öppnar du det jobb som du vill visa i Broadbean.
2. I avsnittet **publiceringar** väljer du ellips-knappen (**...**) som motsvarar Broadbean och markerar sedan **visa**.
3. Redigera informationen för projektet i Broadbean-fönstret och publicera sedan jobbet igen. Jobbdetaljer i Attract ändras inte.

### <a name="remove-a-broadbean-job-posting"></a>Ta bort en Broadbean jobbpublicering

Du kan ta bort en jobbpublicering från Broadbean som du behöver.

1. I Attract öppnar du det jobb som du vill ta bort.
2. I avsnittet **publiceringar** väljer du ellips-knappen (**...**) som motsvarar Broadbean och markerar sedan **ta bort publicering**.

När Broadbean tar bort jobbet har Broadbean-artikeln i Attract en **Publicera nu**-knapp. Förekomsten av den här knappen anger att jobbet har tagits bort och kan publiceras igen.

### <a name="troubleshoot-the-broadbean-integration"></a>Felsöka Broadbean-integrering

Om du har problem med att publicera ett jobb i Broadbean kan du försöka med följande steg.

1. Kontrollera att autentiseringsuppgifterna för Broadbean som du angav i Attract är korrekta.
2. Om autentiseringsuppgifterna är korrekta kan du kontakta [Broadbean-support](https://www.broadbean.com/resources/support/).
3. Om problemet kvarstår kontaktar du [Microsoft support](./talent-support.md).
