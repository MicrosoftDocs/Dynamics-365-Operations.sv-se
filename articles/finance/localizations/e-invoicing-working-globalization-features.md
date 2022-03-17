---
title: Komponenter för globaliseringsfunktion
description: Detta ämne ger en översikt över globaliseringstjänsternas komponenter.
author: dkalyuzh
ms.date: 02/11/2022
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
ms.openlocfilehash: 87d7dd231b9ccda7761c91f129659c18039f3299
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371826"
---
# <a name="globalization-feature-components"></a>Komponenter för globaliseringsfunktion

[!include [banner](../includes/banner.md)]

En globaliseringsfunktion är en uppsättning komponenter som definierar reglerna för dataomvandling i ER-konfigurationer (elektronisk rapportering). I dessa komponenter finns instruktioner om hur du bearbetar elektroniska dokument och sedan skickar dem till eller tar emot dem från externa kanaler. De omfattar också villkor som definierar när en funktion ska köras för inkommande affärsdata.

Alla komponenter är beroende av varandra. Med globaliseringsfunktioner är det enkelt att skapa och underhålla det här beroendet, stödja livscykelhantering och versioner av komponenteruppsättningen.

## <a name="access-electronic-invoicing-feature-components"></a>Få åtkomst till funktionskomponenter för e-fakturering 

1. Logga in på ditt konto för Regelkonfigurationstjänst (RCS).
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Funktioner**, välj panelen **e-faktura**.

    Globaliseringsfunktioner har flera komponenter. Sidan **Funktioner för e-fakturering** innehåller en separat flik för respektive komponent.

    - **Version** – Den här komponenten stöder livscykelhantering för funktionen. Du kan använda den för att hantera statusen för olika versioner av funktionen.
    - **Konfigurationer** – Med hjälp av den här komponenten kan du hantera, visa och redigera relaterade ER-format och formatmappningskonfigurationer som används i bearbetningsförloppet.
    - **Inställningar** – den här komponenten gör det möjligt för användare med globaliseringstjänster, t.ex. en e-faktureringstjänst, att hantera inställningen av den relaterade funktionsversionen. Därför stöder den flexibla uppföranden av kommunikations- och svarsregler.
    - **Miljöer** – Med den här komponenten kan användare med globaliseringstjänster, t.ex. en e-faktureringstjänst, hantera miljön där funktionsversionsinställningarna används. De kan också bevilja behörigheter till de användare som ska ha åtkomst till inställningarna för funktionsversionen.
    - **Organisationer** – Med den här komponenten kan användarna dela funktionen med externa organisationer.
    - **Taggar** – Med hjälp av den här komponenten kan du tagga funktioner som kan användas i globaliseringsplanen som referens.
