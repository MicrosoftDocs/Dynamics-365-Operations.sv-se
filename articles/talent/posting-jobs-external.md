---
title: Publicera jobb från Attract på externa karriärwebbplatser
description: Det här avsnittet beskriver hur du använder Dynamics 365 Talent - Attract för att publicera jobb till externa rekryteringswebbplatser
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
ms.openlocfilehash: 919cec773d5e57e8f5429e31872db7ed658e969b
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008092"
---
# <a name="post-jobs-to-broadbean"></a>Publicera jobb till Broadbean

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Talent: Attract hjälper dig att få den talang du behöver genom att låta dig publicera dina jobb direkt från Attract till Broadbean. När du [skapar ett jobb](./creating-jobs-attract.md) behöver du bara klicka på en knapp för att placera jobbet framför alla potentiella jobbkandidater på Broadbean.

Publicering av jobb till Broadbean kräver en lämplig Broadbean-licens. Broadbean erbjuder olika produkter och planer. Om du vill ha mer information om Broadbean licensiering och priser [kontakta Broadbean](https://www.broadbean.com/contact-us/).

Om du är en administratör som behöver mer information om hur du konfigurerar Broadbean-integrering med Attract, se [Ange inställningar för externa jobbtavlor](./attract-admin-job-board-settings.md).

## <a name="post-jobs-to-broadbean"></a>Publicera jobb till Broadbean

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
2. På fliken **publiceringar** väljer du ellips-knappen (**...**) som motsvarar Broadbean och markerar sedan **visa**.

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

### <a name="troubleshoot-job-posting-to-broadbean"></a>Felsökning av jobbpublicering i Broadbean

Om du har problem med att publicera ett jobb i Broadbean kan du försöka med följande steg.

1. Kontrollera att autentiseringsuppgifterna för Broadbean som du angav i Attract är korrekta.
2. Om autentiseringsuppgifterna är korrekta kan du kontakta [Broadbean-support](https://www.broadbean.com/resources/support/).
3. Om problemet kvarstår kontaktar du [Microsoft support](./talent-support.md).

## <a name="see-also"></a>Se även

[Skapa jobb](./creating-jobs-attract.md)

[Ange inställningar för externa jobbtavlor](./attract-admin-job-board-settings.md)
