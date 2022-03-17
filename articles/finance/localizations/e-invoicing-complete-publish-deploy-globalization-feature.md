---
title: Slutföra, publicera och distribuera en globaliseringsfunktion
description: Detta ämne innehåller information om funktionerna för globaliseringslivscykel.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: a842a3ba31c0a8e0d80ad1856d9d6d861a8514ea
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371785"
---
# <a name="complete-publish-and-deploy-a-globalization-feature"></a>Slutföra, publicera och distribuera en globaliseringsfunktion

[!include [banner](../includes/banner.md)]

## <a name="electronic-invoicing-feature-versions"></a>Funktionsversioner för e-fakturering

Funktionerna för e-fakturering uppdateras genom olika versioner. När en ny version skapas ökar versionsnumret automatiskt.

Versioner av e-faktureringsfunktioner har en livscykel med upp till tre statusar:

- **Utkast** – När en funktionsversion har detta statusvärde kan du redigera dess konfigurationsattribut och dess artefakter (till exempel filformatkonfigurationer).
- **Slutförd** – Den här statusen anger att du är färdig med redigeringen av funktionsversionen och inte tänker göra fler uppdateringar av den. Om en funktionsversion har denna status kan du inte längre redigera vare sig den eller dess komponenter.
- **Publicerad** – Denna status anger att funktionsversionen har publicerats i den globala databas som är associerad med din organisation. Om en funktionsversion har denna status kan du inte längre redigera vare sig den eller dess komponenter.

Du kan ange ett **Gäller från**-datum för en ny version av en e-faktureringsfunktion. På det här sättet kan du definiera en standardversion som kan användas eller som kan skrivas över när funktionen distribueras till tjänstemiljön.

Följ de här stegen om du vill ändra statusen för en e-faktureringsfunktionsversion.

1. Logga in på ditt konto för Regelkonfigurationstjänst (RCS).
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Funktioner**, välj panelen **e-faktura**.
3. På väntra delen av sidan **Funktioner för e-fakturering** välj er du funktionen för e-fakturering.
4. På fliken **Versioner** på högra delen av sidan väljer du versionen.
5. Välj **Ändra status** och sedan **Slutför** (om aktuell status är **Utkast**) eller **Publicerad** (om aktuell status är **Slutförd**).
6. Markera **Ja** i meddelanderutan för att bekräfta begäran.

Den manuella ändringen från statusen **Slutförd** till **Publicerad** är valfri. Versioner av funktionen e-fakturering uppdateras automatiskt till statusen **Publicerad** när de distribueras till tjänstemiljön.

Du kan spåra statusen i kolumnen **Funktionsversionsstatus** på fliken **Versioner**.

## <a name="deploy-feature-versions"></a>Distribuera funktionsversioner

I RCS använder du kommandot **Disitribuera** för att publicera en e-faktureringsfunktionsversion i måltjänstmiljön eller det anslutna programmet.

1. På väntra delen av sidan **Funktioner för e-fakturering** välj er du funktionen för e-fakturering.
2. På fliken **Versioner** till höger på sidan väljer du den version av e-faktureringsfunktionen som du vill distribuera till tjänstemiljön eller det anslutna programmet. Den valda versionen måste ha statusen **Slutförd** eller **Publicerad**.
3. Välj **Distribuera** och sedan ett eller båda av följande alternativ för att definiera distributionens mål:

    - **Anslutet program** – Den konfiguration som tillhandahålls av programinställningarna skrivs i instansen av Microsoft Dynamics 365 Finance eller Dynamics 365 Supply Chain Management som tidigare associerats med den.
    - **Servicemiljö** – E-faktureringsfunktionen distribueras till tjänstemiljön. E-fakturering är sedan redo att ta emot och bearbeta elektroniska dokument som Ekonomi och Supply Chain Management skickar.

> [!NOTE]
> Vanligtvis ändrar du parametrarna för den elektroniska rapporteringsfunktionen (ER) som måste distribueras till tjänstemiljön. Ändringar i det anslutna programmet kommer att vara sällsynta. Du bör bara distribuera nya versioner till det anslutna programmet när du ändrar motsvarande parametrar för programmet.

Ta reda på om en specifik version av en e-faktureringsfunktion distribueras till en specifik miljö, granska informationen på fliken **Miljöer**.

## <a name="remove-feature-versions"></a>Ta bort funktionsversioner

I RCS kan du välja **Avbryt** om du vill ta bort en specifik version av e-faktureringsfunktionen från en tjänstemiljö, om den distribuerats där.

> [!IMPORTANT]
> Knappen **Avbryt** fungerar endast för tjänstemiljöer. Den tar inte bort något från det anslutna programmet för den aktuella e-faktureringsfunktionen.

## <a name="rebase-electronic-invoicing-features"></a>Basera om funktioner för e-fakturering

När en funktion för e-fakturering härleds från en annan kan du välja **Basera om** för att uppdatera den härledda funktionen med de ändringar som har gjorts i den ursprungliga (överordnade) funktionen.

Om du vill ombasbasa en härledd version av en funktion som du skapat gör du så här.

1. Hämta den senaste versionen av funktionen genom att importera den från den globala databasen. Mer information finns i [Importera funktion från global databas](e-invoicing-import-feature-global-repository.md).
2. Välj den funktion som ska återbyggas i listan över funktioner.
3. På fliken **Versioner** väljer du **Ny** för att skapa en utkastversion.
4. Välj **Basera om**.
5. I dialogrutan **Basera om** väljer du den version av funktionen som ska baseras om till.
6. Välj **OK**.
7. Granska funktionskomponenter och gör nödvändiga ändringar.
8. Välj **ändra status** om du vill slutföra funktionen basera om. När ombaseringen är slutförd kan du utföra ytterligare åtgärder.

## <a name="get-a-specific-version-of-electronic-invoicing-features"></a>Skaffa en specifik version av e-faktureringsfunktioner

När du skapar en ny version av en e-faktureringsfunktion skapas en kopia av den senaste funktionsversionen i systemet. Om du vill använda en tidigare version av funktionen som bas för en ny version väljer du versionen och sedan **Hämta versionskommando**. En ny utkastversion av funktionen skapas som är en kopia av den valda versionen.
