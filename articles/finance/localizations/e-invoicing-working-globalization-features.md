---
title: Komponenter för globaliseringsfunktion
description: Detta ämne ger en översikt över globaliseringstjänsternas komponenter.
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
ms.openlocfilehash: 94e2d118c332a15f41f33184f5e44b0fdaccd000
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275239"
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
