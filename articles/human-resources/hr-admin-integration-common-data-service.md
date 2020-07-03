---
title: Konfigurera Common Data Service-integrering
description: Du kan aktivera eller inaktivera integration mellan Common Data Service och Dynamics 365 Human Resources. Du kan också visa synkroniseringsinformation, ta bort uppföljningsdata och synkronisera om en enhet för att hjälpa till att felsöka data från de två miljöerna.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7aad8217d48917d6855046a6810fe994f5564d94
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431324"
---
# <a name="configure-common-data-service-integration"></a>Konfigurera Common Data Service-integrering

Du kan aktivera eller inaktivera integration mellan Common Data Service och Dynamics 365 Human Resources. Du kan också visa synkroniseringsinformation, ta bort uppföljningsdata och synkronisera om en enhet för att hjälpa till att felsöka data från de två miljöerna.

När du stänger av integrationen kan användarna göra ändringar i personal eller Common Data Service, men dessa ändringar synkroniseras inte mellan de två miljöerna.

Som standard inaktiveras dataintegrering mellan personal och Common Data Service.

Du kanske vill inaktivera integration i följande situationer:

- Du fyller i data via datahanteringsramverket och måste importera data flera gånger för att de ska få rätt status.

- Det finns problem med data i personal eller Common Data Service. Om du inaktiverar integration kan du ta bort en post i en miljö utan att ta bort den i den andra. När du aktiverar integreringen igen kommer posten i miljön där den inte togs bort att synkroniseras till den miljö där den togs bort. Synkroniseringen påbörjas nästa gång batchjobbet **Common Data Service-integrering missade begärd synkronisering** körs.

> [!WARNING]
> När du stänger av dataintegreringen måste du se till att du inte redigerar samma post i båda miljöerna. När du slår på integrationen igen synkroniseras posten som du senast redigerade. Om du inte gör samma ändringar i den här posten i båda miljöerna kan det därför hända att data går förlorade.

## <a name="access-the-common-data-service-integration-page"></a>Öppna sidan Common Data Service-integration

1. I personalinstansen där du vill visa eller konfigurera inställningar för integrering med Common Data Service väljer du panelen **systemadministration**.

    [![Panelen Systemadministration](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Välj fliken **Länkar**.

    [![Fliken Länkar](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. Under **Integrationer**, välj **Common Data Service konfiguration**.

    [![Common Data Service konfigurationslänk](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a>Aktivera och inaktivera dataintegrering mellan personal och Common Data Service

- Aktivera integration genom att ställa in alternativet **Aktivera integration till Common Data Service** till **Ja**.

    > [!NOTE]
    > När du aktiverar integrationen kommer data att synkroniseras nästa gång som batchjobbet **Common Data Service-integrering missade begärd synkronisering** körs. Alla data måste vara tillgängliga när batch-jobbet har slutförts.

- Om du vill stänga av integrationen ställer du in alternativet på **Nej**.

[![Aktivera eller inaktivera Common Data Service-integreringen](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)

## <a name="view-data-integration-details"></a>Visa information om dataintegrering

På snabbfliken **administration** på sidan **Common Data Service-integration** kan du se hur posterna är kopplade till varandra mellan personal och Common Data Service.

- Om du vill visa posterna för en entitet markerar du enheten i fältet **CDS-enhetsnamn**. I rutnätet visas alla poster som är länkade till den valda enheten.

[![Visa posterna för en enhet](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)

> [!NOTE]
> Alla Common Data Service-entiteter visas inte för närvarande i listan. Endast enheter som stöder användning av anpassade fält visas i rutnätet. Nya enheter blir tillgängliga genom kontinuerliga uppdateringar av personal.

Rutnätet innehåller följande fält:

- **CDS-enhetsnamn** – namnet på enheten i Common Data Service.
- **CD-enhetsreferens** – identifieraren aom Common Data Service använder för att identifiera en post. Detta värde är detsamma som ett värde för personalvärdet **RecId**. Du kan hitta identifieraren när du öppnar Common Data Service entiteten i Microsoft Excel.
- **Namn på personalenhet** – den enhet som senast synkroniserade data till Common Data Service. Entiteten kan antingen ha Common Data Service prefixet eller ett annat prefix.
- **Personalreferens** – **RecId**-värdet som är kopplat till posten i personal.
- **Togs bort från CDS** – ett värde som anger om posten togs bort från Common Data Service.

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a>Ta bort kopplingen för en post i personal från Common Data Service

Om du får problem under synkroniseringen mellan personal och Common Data Service kan du kanske lösa dem genom att avmarkera spårningen och låta spårningstabellen synkroniseras igen. Om du tar bort kopplingen och sedan ändrar eller tar bort en post i Common Data Service synkroniseras inte ändringarna med personal. Om du ändrar i personal skapas en ny spårningspost och posten uppdateras i Common Data Service.

- Om du vill ta bort en posts koppling mellan personal och Common Data Service, markera enheten i fältet **CDS-enhetsnamn** och väljer sedan **Rensa uppföljningsinformation**.

[![Rensa uppföljningsinformation](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)

Information om hur du kör en fullständig synkronisering på entiteten efter att du har rensat spårningen finns i nästa procedur.

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a>Synkronisera en enhet mellan personal och Common Data Service

Gör på följande sätt när:

- Ändringar från Common Data Service tar för lång tid att visas i personal.

- Du måste uppdatera spårningstabellen när du har avmarkerat spårningen.

Så här kör du en fullständig synkronisering på en enhet mellan personal och Common Data Service:

1. Välj entitet i fältet **CDS entitetsnamn**.

2. Välj **Synkronisera nu**.

[![Köra en fullständig synkronisering](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)


