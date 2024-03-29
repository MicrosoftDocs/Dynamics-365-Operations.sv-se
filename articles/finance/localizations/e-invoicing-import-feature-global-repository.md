---
title: Importera funktioner från den globala databasen
description: I denna artikel beskrivs hur du importerar globaliseringsfunktioner från den globala databasen.
author: gionoder
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 5a72673e17c5653d43b60d3348d5518e09c40a15
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278324"
---
# <a name="import-features-from-the-global-repository"></a>Importera funktioner från den globala databasen

[!include [banner](../includes/banner.md)]

Den globala databasen innehåller funktioner för e-fakturering som delas med din konfigurationsleverantör. Alla funktioner för e-fakturering som Microsoft tillhandahåller delas med alla företag. Du har automatiskt tillgång till alla funktioner för e-fakturering som Microsoft släpper och publicerar i den globala databasen.

Om du vill börja arbeta med funktioner för e-fakturering som delas med din konfigurationsleverantör importerar du dem till din instans av Regulatory Configuration Service (RCS) från den globala databasen. Granska sedan funktionsdetaljerna, till exempel konfigurationerna för Elektronisk rapportering (ER) och bearbetningsförlopp.

## <a name="import-a-feature-from-the-global-repository"></a>Importera en funktion från den globala databasen

1. Logga in på RCS-kontot.
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Funktioner**, välj panelen **e-faktura**.
3. Välj **Importera** om du vill öppna sökningen **Importera funktion från den globala databasen**.
4. Om du vill bläddra i de e-faktureringsfunktionerna som är tillgängliga i den globala databasen för en viss konfigurationsleverantör, synkroniserar du organisationens RCS-instans genom att välja **Synkronisera**. När synkroniseringen är klar uppdateras listan med tillgängliga funktioner för e-fakturering från den globala databasen. Denna uppdatering kan ta några minuter.
5. Välj den funktion du vill importera och välj sedan **Importera**.

För att visa den importerade funktionen för e-faktura, se till att välja korrekt konfigurationsleverantör. Som standard filtreras funktioner som skapats av den aktiva konfigurationsprovidern automatiskt bort. Du kan justera filtret så att det visar funktioner som har skapats av andra leverantörer, till exempel Microsofts konfigurationsleverantör.

Du kan nu arbeta med den importerade funktionen. Du kan granska dess information och skapa en ny funktion genom att använda den importerade funktionen som en mall.

> [!NOTE]
> Du kan bara ändra en funktion om denna har skapats av konfigurationsprovidern som för närvarande är aktiv. Du kan skapa en ny funktion genom att använda den ursprungliga funktionen som bas. Du kan sedan utföra nödvändiga ändringar eller ställa in parametrarna.

När Microsoft eller något annat företag som delar globaliseringsfunktionerna med ditt företag uppdaterar funktioner som du har importerat kan du söka efter uppdaterade versioner genom att välja **Sök efter funktionsuppdateringar** i avsnittet **Relaterade inställningar** i arbetsytan **Globaliseringsfunktioner**.

Om det finns uppdateringar för en funktion som du använder som mall kan du importera en ny version efter att du synkroniserat listan med publicerade funktioner i den globala databasen.
