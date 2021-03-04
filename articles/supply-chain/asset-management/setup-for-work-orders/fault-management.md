---
title: Felhantering
description: I det här avsnittet beskrivs felhantering i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 72d6c8d750a5a0903017b4c77b3ce5d9521cf99b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437571"
---
# <a name="fault-management"></a>Felhantering

[!include [banner](../../includes/banner.md)]

 

I tillgångshantering kan du använda feldesignern för att ställa in felsymtom, felområden och feltyper för tillgångstyper. På så sätt kan du hantera fel som upptäcks på tillgångar. Dessutom kan felorsaker och förslag om hur du korrigerar fel registreras på en arbetsorder.

Processen för felregistrering och felhantering består av dessa steg.

1. Skapa en lista med felsymptom, felområden och feltyper som kan uppstå på dina tillgångstyper.
2. Ställ in symptom, felområden och feltyper i feldesignern.

Här följer några exempel på hur du förstår skillnaden mellan felsymtom, felområden och feltyper.

**Felsymptom:**

- Ej balanserade spänningar
- Kortslutning
- Buller
- Läckage
- Vibrationer

**Felområden:**

- Elektriskt
- Mekaniskt
- Hydrauliskt
- Pneumatiskt

**Feltyper:**

- Felaktig huvudstatorlindning
- Trasig diod
- Smutsiga lindningar
- Defekt generator
- Defekt sensor

## <a name="create-fault-symptoms"></a>Skapa felsymptom

Följ dessa steg för att skapa en lista över symptom som kan användas i feldesignern.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Felsymptom**.
2. Välj **Ny** för att skapa en post.
3. Ange ett namn på felsymptomet i fältet **Felsymptom**.
4. Ange en beskrivning i fältet **beskrivning**.
5. Välj **Spara**.

## <a name="create-fault-areas"></a>Skapa felområden

Följ dessa steg för att skapa en lista över områden eller platser som kan användas i feldesignern.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Felområden**.
2. Välj **Ny** för att skapa en post.
3. Ange ett namn på felområdet i fältet **Felområde**.
4. Ange en beskrivning i fältet **beskrivning**.
5. Välj **Spara**.

## <a name="create-fault-types"></a>Skapa feltyper

Följ dessa steg för att skapa en lista över feltyper som kan användas i feldesignern.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Feltyper**.
2. Välj **Ny** för att skapa en post.
3. Ange ett namn på feltypen i fältet **Feltyp**.
4. Ange en beskrivning i fältet **beskrivning**.
5. Välj **Spara**.

## <a name="set-up-the-fault-designer"></a>Ställa in feldesignern

I feldesignern ställer du in feldata för tillgångstyper.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Feldesigner**.
2. I det vänstra fönstret väljer du den typ av tillgång som du vill ställa in en felpost för.
3. På snabbfliken **Felsymptom** väljer du **Lägg till rad** och väljer sedan ett felsymptom i fältet **Felsymptom**.
4. På snabbfliken **Felområde** väljer du **Lägg till rad** och väljer sedan ett felområde i fältet **Felområde**.
5. På snabbfliken **Feltyp** väljer du **Lägg till rad** och väljer sedan en feltyp i fältet **Feltyp**.
6. Om du snabbt vill skapa kombinationer av alla befintliga felsymptom, felområden och feltyper för den valda tillgångstypen väljer du **Skapa felkombinationer**. Den här funktionen är användbar om du har lagt till många felsymptom, felområden och feltyper. Det är enklare att ta bort raderna för de kombinationer som inte är relevanta för tillgångstypen än att skapa nya rader manuellt.

    > [!NOTE]
    > Om du vill kopiera inställningarna för felsymptom, felområden och feltyper från en tillgångstyp till den valda tillgångstypen väljer du **Kopiera från tillgångstyp**.

7. Spara ändringarna genom att klicka på **Spara**.

![Feldesignersida](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a>Skapa felorsaker

Följ dessa steg om du vill skapa en lista med kända felorsaker som kan läggas till i en arbetsorder eller en underhållsbegäran.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Felorsaker**.
2. Välj **Ny** för att skapa en post.
3. Ange ett namn på felorsaken i fältet **Felorsak**.
4. Ange en beskrivning i fältet **beskrivning**.
5. Välj **Spara**.

## <a name="create-fault-remedies"></a>Skapa fellösningar

Följ dessa steg om du vill skapa en lista med förslag på lösningar och reparationer som kan läggas till i en arbetsorder eller en underhållsbegäran.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Fellösningar**.
2. Välj **Ny** för att skapa en post.
3. Ange ett namn på fellösningen i fältet **Fellösning**.
4. Ange en beskrivning i fältet **beskrivning**.
5. Välj **Spara**.

> [!NOTE]
> Du kan ändra namnen på dina felsymtom, felområden, feltyper, felorsaker och fellösningar. Namnändringarna återspeglas automatiskt i de relaterade felregistreringarna.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]