---
title: Manuell uppdatering av tillgångsräknare
description: Det här avsnittet beskriver manuell uppdatering av tillgångsräknare i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875905"
---
# <a name="manual-update-of-asset-counters"></a>Manuell uppdatering av tillgångsräknare

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Räknare används för att skapa registreringar för en tillgång angående t.ex. antal timmar i drift eller antalet producerade kvantiteter.

Om den valda räknartypen för en räknare är inställd på att ärva räknarvärden (**Tillgångshantering** > **Inställningar** > **Tillgångstyper** > **Räknare** >  snabbfliken **Allmänt** > växlingsknappen **Ärv värden för tillgångsräknare** inställd på "Ja"), och när du sedan skapar en ny räknarrad av den typen, uppdateras alla underordnade tillgångar som använder samma räknartyp automatiskt.

I **Alla tillgångar** kan du skapa tim- eller kvantitetsräknarregistreringar för en tillgång, baserat på dina avläsningar av tillgången.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**.

2. Välj tillgång i listan och klicka på **Räknare**. I formuläret **Tillgångsräknare** visas en lista över alla tidigare räknarregistreringar för den valda tillgången.

3. Klicka på **Ny** om du vill skapa en ny registrering. Tillgångens ID infogas automatiskt.

4. Välj relevant räknare i fältet **Räknare**. Endast räknare som hör till den tillgångstyp som valts i tillgången är tillgängliga. Den relaterade enheten infogas automatiskt i fältet **Enhet**.

5. Välj datum och tid för räknarregistreringen.

6. I fältet **Värde** anger du numret sedan den senaste räknarregistreringen eller, i fältet **Sammanlagt värde**, infogar du det totala antalet.

- Om du installerar en ny räknare för en tillgång fysiskt måste du registrera ändringen i tillgången i **Tillgångsräknare**. Sedan måste du skapa två registreringsrader med identiska tidsstämplar, och på raden för den nya räknaren markerar du kryssrutan **Återställ räknare**. När du skapar de två registreringsraderna måste den första raden vara för den räknare som du ersätter. I fältet **Summor** är den totala räknarsumman summan av alla registrerade värden på den räknartypen.  
- Om kryssrutan **Återställ räknare** har markerats för en tillgång med en underhållsplan med intervalltypen "En gång från..." eller "När...nås" är räknaren fortfarande aktiv på den nya räknarraden, eftersom du skapar en separat räknarrad och börjar om med en ny räknare.

![Figur 1](media/11-work-orders.png)


Om du behöver göra räknarregistreringar för flera tillgångar kan du utföra dem i **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Tillgångsräknare**.

>[!NOTE]
>Du kan ställa in ett intervall för att definiera avvikelser i manuella räknarregistreringar, och vilken typ av meddelande som ska visas om registreringarna ligger utanför det definierade intervallet. Information om hur du ställer in räknare finns i avsnittet [Räknare](../setup-for-objects/counters.md).
