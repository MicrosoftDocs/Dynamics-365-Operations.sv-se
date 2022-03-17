---
title: Arbeta med konfigurationer
description: Detta ämne ger en översikt över huvudscenariot för att arbeta med ER-konfigurationer (elektronisk rapportering) från arbetsytan för globaliseringsfunktioner.
author: dkalyuzh
ms.date: 01/26/2022
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
ms.openlocfilehash: 4318399ee58ed54b29f8d360345b8930238ea9f2
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371833"
---
# <a name="work-with-configurations"></a>Arbeta med konfigurationer

[!include [banner](../includes/banner.md)]

Konfigurationer för elektronisk rapportering (ER) är en av huvuduppsättningarna med komponenter i e-faktureringsfunktioner. En ER-konfiguration innehåller inställningar av filstrukturen och en uppsättning transformeringsregler för transformering av data på två sätt:

- **ER-formatkonfiguration för export** – Denna konfiguration transformerar data från den enhetliga interna strukturen (ER-modellen) till det elektroniska filformatet.
- **ER-formatkonfiguration för import** – Denna konfiguration transformerar data från elektroniskt filformat till enhetlig intern struktur (ER-modell).

Förutom att generera utgående elektroniska filer i det fördefinierade formatet används ER-konfigurationer ofta för att parsa inkommande meddelanden från externa webbtjänster som svar. Den här funktionen gör det lättare att skapa konfigurerbar logik för att få resultaten av kommunikationen med externa kanaler, konvertera resultaten (koder, meddelanden och loggar) till den användarläsbara strukturen, och sedan överföra denna information till klientprogrammet.

Om du vill börja använda ER-konfigurationer **i din e-faktureringsfunktion måste du koppla dem till funktionen och göra dem tillgängliga på fliken Konfigurationer** för den aktuella funktionsversionen. Du kan arbeta med en länkad ER-konfiguration genom att välja **Lägg till**, **Ta bort**, **Redigera** eller **Visa**.

Innan du kan lägga till en länk i en ER-konfiguration måste konfigurationen finnas i databasen Regulatory Configuration Service (RCS). Om du vill granska ER-konfigurationerna som är tillgängliga i din RCS-databas, följ dessa steg.

1. Logga in på RCS-kontot.
2. På arbetsytan **Elektronisk rapportering**, i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.

Information om hur du skapar en ny ER-konfiguration eller importerar en befintlig ER-konfiguration från den globala databasen finns i [Elektronisk rapportering](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Om du vill justera en länkad ER-konfiguration väljer du **Redigera** på fliken **Konfigurationer** för aktuell faktureringsfunktion. En version av ER-konfigurationen skapas automatiskt av systemet. Om den aktuella versionen inte skapats av den aktiva konfigurationsprovidern skapar systemet en härledd version som använder din konfigurationsleverantör. Om den aktuella versionen har skapats av den aktiva konfigurationsprovidern skapas en ny version automatiskt av systemet. I båda fall kan du ändra den version som skapas och sedan automatiskt göra alla uppdateringar som behövs.
