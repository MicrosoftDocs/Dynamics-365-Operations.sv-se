---
title: Manuell uppdatering av tillgångsräknare
description: Det här avsnittet beskriver manuell uppdatering av tillgångsräknare i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6dfea7ca166948f507a1cdea20f3e4cce16080ce
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219495"
---
# <a name="manual-update-of-asset-counters"></a>Manuell uppdatering av tillgångsräknare

[!include [banner](../../includes/banner.md)]



Räknare används för att skapa registreringar för en tillgång, t.ex. registreringar om antalet timmar som tillgången har varit i drift eller den kvantitet som har producerats.

Den räknartyp som valts för en räknare kan vara inställd på att ärva räknarvärden. Med andra ord ställs alternativet **Ärv värden för tillgångsräknare** på **Ja** på snabbfliken **allmänt** på sidan **räknare** (**Tillgångshantering** > **Inställningar** > **Tillgångstyper** > **Räknare**). När du i detta fall skapar en ny räknarrad av den typen, uppdateras alla underordnade tillgångar som använder samma räknartyp automatiskt.

På sidan I **Alla tillgångar** kan du skapa tim- eller kvantitetsräknarregistreringar för en tillgång, baserat på dina avläsningar av tillgången.

1. Välj **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**.

2. Välj tillgången och sedan, i åtgärdsfönstret på fliken **Tillgång** i gruppen **Förebyggande** väljer du **Räknare**. Sidan **Tillgångsräknare** visas en lista över alla tidigare räknarregistreringar som har gjorts för den valda tillgången.

3. Skapa en ny registrering genom att välja **Nytt**. Tillgångs-ID anges automatiskt i fältet **Tillgång**.

4. Välj relevant räknare i fältet **Räknare**. Endast räknare som hör till den tillgångstyp som valts i tillgången är tillgängliga för val. Den relaterade enheten anges automatiskt i fältet **Enhet**.

5. I fältet **Registrerad** välj datum och tid för räknaregistreringen.

6. I fältet **värde** anger du numret sedan den senaste räknarregistreringen. I fältet **aggregerad värde** kan du också ange det totala inventeringsnumret.

Observera följande:

- Om du installerar en ny räknare för en tillgång fysiskt måste du registrera ändringen i tillgången på sidan **Tillgångsräknare**. Sedan måste du skapa två registreringsrader som har identiska tidsstämplar. Den första raden måste vara för den räknare som du ersätter. På raden som är relaterad till den nya räknaren markerar du kryssrutan **Återställ räknare**. I fältet **Summor** är den totala räknarsumman summan av alla registrerade värden på den räknartypen.

- Om kryssrutan **Återställ räknare** har markerats för en tillgång med en underhållsplan med intervalltypen "En gång från..." eller "När...nås" är räknaren fortfarande aktiv på den nya räknarraden, eftersom du skapar en separat räknarrad och börjar om med en ny räknare.

Bilden nedan visar ett exempel på sidan **Tillgångsräknare**.

![Figur 1](media/11-work-orders.png)

På sidan **Tillgångsräknare** (**Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Tillgångsräknare**) kan du göra räknarregistreringar på flera tillgångar samtidigt, efter behov.

>[!NOTE]
>Du kan ställa in ett intervall för att definiera avvikelser i manuella räknarregistreringar. Du kan även ange vilken typ av meddelande som visas om registreringarna ligger utanför det definierade intervallet. Mer information om hur du ställer in räknare finns i [räknare](../setup-for-objects/counters.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]