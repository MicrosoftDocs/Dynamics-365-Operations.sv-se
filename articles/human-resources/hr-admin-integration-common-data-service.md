---
title: Konfigurera Dataverse-integrering
description: I detta ämne beskrivs integreringen mellan Microsoft Dataverse och Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c4e68142045b72b139bdda8be707a73e21e568fd
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065461"
---
# <a name="configure-dataverse-integration"></a>Konfigurera Dataverse-integrering


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan aktivera eller inaktivera integrering mellan Microsoft Dataverse och Dynamics 365 Human Resources. Du kan också visa synkroniseringsinformationen, rensa spårningsdata och synkronisera om ett register för att hjälpa till att felsöka dataproblem från de två miljöerna.

> [!NOTE]
> Mer information om Dataverse (tidigare Common Data Service) och terminologiuppdateringar finns i [Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

När du stänger av integreringen kan användarna göra ändringar i personal eller Dataverse, men dessa ändringar synkroniseras inte mellan de två miljöerna.

Som standard inaktiveras dataintegrering mellan personal och Dataverse.

Du kanske vill inaktivera integrering i följande situationer:

- Du fyller i data via datahanteringsramverket och måste importera data flera gånger för att de ska få rätt status.

- Det finns problem med data i personal eller Dataverse. Om du inaktiverar integrering kan du ta bort en post i en miljö utan att ta bort den i den andra. När du aktiverar integreringen igen kommer posten i miljön där den inte togs bort att synkroniseras till den miljö där den togs bort. Synkroniseringen påbörjas nästa gång batchjobbet **Dataverse-integrering missade begärd synkronisering** körs.

> [!WARNING]
> När du stänger av dataintegreringen måste du se till att du inte redigerar samma post i båda miljöerna. När du slår på integreringen igen synkroniseras posten som du senast redigerade. Om du inte gör samma ändringar i den här posten i båda miljöerna kan det därför hända att data går förlorade.

## <a name="access-the-dataverse-integration-page"></a>Öppna sidan Dataverse-integrering

1. I personalinstansen där du vill visa eller konfigurera inställningar för integrering med Dataverse väljer du panelen **systemadministration**.

    [![Panelen Systemadministration.](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Välj fliken **Länkar**.

    [![Fliken Länkar.](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. Under **Integreringer**, välj **Dataverse konfiguration**.

    [![Dataverse-konfigurationslänk.](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a>Aktivera och inaktivera dataintegrering mellan personal och Dataverse

- Ställ in alternativet **Aktivera Dataverse-integrering** som **Ja** på sidan **Microsoft Dataverse-integrering** för att aktivera integrering.

    > [!NOTE]
    > När du aktiverar integreringen kommer data att synkroniseras nästa gång som batchjobbet **Dataverse-integrering missade begärd synkronisering** körs. Alla data måste vara tillgängliga när batch-jobbet har slutförts.

- Om du vill stänga av integreringen ställer du in alternativet på **Nej**.

[![Aktivera eller inaktivera Dataverse-integreringen.](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)

> [!WARNING]
> Vi rekommenderar att du inaktiverar Dataverse integrering när du utför dataflyttningsuppgifter. Stora dataöverföringar kan påverka prestanda betydligt. Exempelvis kan överföringar av 2 000 medarbetare ta flera timmar när integreringen är aktiverad och mindre än en timme när den är inaktiverad. Siffrorna i det här exemplet är endast avsedda som demonstrationer. Hur lång tid det tar att importera poster kan variera kraftigt baserat på många faktorer.

## <a name="view-data-integration-details"></a>Visa information om dataintegrering

På snabbfliken **Administration** på sidan **Microsoft Dataverse-integrering** kan du se hur raderna är kopplade till varandra mellan Personal och Dataverse.

- Om du vill visa raderna för ett register markerar du registret i fältet **Dataverse-register**. I rutnätet visas alla rader som är länkade till det valda registret.

> [!NOTE]
> Alla Dataverse-register visas inte för närvarande i listan. Endast register som stöder användning av anpassade fält visas i rutnätet. Nya register blir tillgängliga genom kontinuerliga uppdateringar av Personal.

Rutnätet innehåller följande fält:

- **Dataverse-register** – Namnet på registret i Dataverse.
- **Registerreferens för Dataverse** – Den identifierare som Dataverse använder för att identifiera en post. Detta värde är detsamma som ett värde för personalvärdet **RecId**. Du kan hitta identifieraren när du öppnar Dataverse-registret i Microsoft Excel.
- **Namn på Personal-entitet** – den Personal-enhet som senast synkroniserade data till Dataverse. Entiteten kan antingen ha Dataverse prefixet eller ett annat prefix.
- **Personalreferens** – **RecId**-värdet som är kopplat till posten i personal.
- **Borttaget från Dataverse** – Ett värde som anger huruvida raden tagits bort från Dataverse.

> [!NOTE]
> Poster i Personal motsvarar rader i Dataverse.

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a>Ta bort kopplingen för en Personal-post från en Dataverse-rad

Om du får problem under synkroniseringen mellan personal och Dataverse kan du kanske lösa dem genom att avmarkera spårningen och låta spårningstabellen synkroniseras igen. Om du tar bort kopplingen och sedan ändrar eller tar bort en rad i Dataverse synkroniseras inte ändringarna med Personal. Om du utför ändringar i Personal skapas en ny spårningspost och raden uppdateras i Dataverse.

- Om du vill ta bort kopplingen mellan en Personal-post och en Dataverse-rad väljer du registret i fältet **Dataverse-register** och sedan **Rensa spårningsinformation**.

[![Rensa spårningsinformation.](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)

Se nästa procedur för att köra en fullständig synkronisering på registret efter det att du har rensat spårningen.

## <a name="sync-a-table-between-human-resources-and-dataverse"></a>Synkronisera ett register mellan Personal och Dataverse

Gör på följande sätt när:

- Ändringar från Dataverse tar för lång tid att visas i personal.

- Du måste uppdatera spårningstabellen när du har avmarkerat spårningen.

Så här kör du en fullständig synkronisering på ett register mellan Personal och Dataverse:

1. Välj registret i fältet **Dataverse-register**.

2. Välj **Synkronisera nu**.

[![Köra en fullständig synkronisering.](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)

## <a name="see-also"></a>Se även

[Dataverse-register](hr-developer-entities.md)<br>
[Konfigurera virtuella Dataverse-register](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Vanliga frågor och svar om virtuella register i Human Resources](hr-admin-virtual-entity-faq.md)<br>
[Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Terminologiuppdateringar](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
