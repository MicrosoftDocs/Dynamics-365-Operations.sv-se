---
title: Bedömningsprofiler
description: I denna artikel beskrivs hur du konfigurerar data för bedömningsprofiler.
author: Weijiesa
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f7408574187ddb099181bd2566c46c52307f603
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850493"
---
# <a name="rating-profiles"></a>Bedömningsprofiler

[!include [banner](../../includes/banner.md)]

En bedömningsprofil påminner om ett logistik kontrakt (men inte ett juridiskt kontrakt). Den används för att bestämma transporttaxor för laster. 

Varje klassificeringsprofil är unik för ett transportföretag. I profilen kan du associera transportföretaget med ett tariffhuvud. Tariffmallen definierar tariffbastilldelning och tariffbasen. Tariffbasen bestämmer tariffen för transportföretaget.

Du kan konfigurera en klassificeringsprofil med hjälp av generisk sida som visar en översikt över alla befintliga. Alternativt kan du konfigurera klassificeringsprofilen direkt från transportföretaget. I båda fallen är informationen som du konfigurerar för värderingsprofilen densamma.

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a>Skapa eller redigera en bedömningsprofil på sidan värderingsprofiler

På sidan **bedömningsprofiler** kan du granska alla tillgängliga bedömningsprofiler. Du kan också redigera befintliga profiler och skapa nya profiler.

1. Gå till **Transporthantering \> Inställningar \> Bedömning \> Bedömningsprofil**.
1. I åtgärdsfönstret, välj **Ny** om du vill lägga till en ny bedömningsprofil i rutnätet eller välja **Redigera** för att redigera en befintlig profil.
1. Ange följande fält i raden för den nya eller befintliga bedömningsprofil:

    - **Bedömningsprofil** – Ange en unik identifierare (ID) för betygsprofilen.
    - **Namn** – Ange ett beskrivande namn för bedömningsprofilen.
    - **Transportföretag** – Välj ett transportföretag. Den bedömningsprofil som du konfigurerar visas också på sidan **Transportföretag** för det valda transportföretaget.
    - **Webbplats** och **Lagerställe** – Välj en webbplats och lagerställe.
    - **Bedömningsmotor** – Välj bedömningsmotor för bedömningsprofilen.
    - **Bedömningsmall** – Välj bedömningsmall för bedömningsprofilen. Du kan använda tariffmallen för att definiera en tariffbastyp och en tariffbas. Mer information finns i [Ställ in tariffhuvuden](set-up-rate-masters.md).
    - **Transporttidsmotor** – Välj motorn för transporttid för värderingsprofilen.
    - **Bränsleindex för transportföretag** – Välj transporttidsmotor och transportföretagets bränsleindex för klassificeringsprofilen.
    - **Effektivt startdatum och tid** och **Effektivt slutdatum och tid** – Definiera den period då bedömningsprofilen ska vara aktiv.

1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a>Skapa en bedömningsprofil direkt på sidan transportföretag

1. Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportföretag**.
1. Välj ett transportföretag i listan.
1. På snabbfliken **Bedömningsprofiler** välj **Ny** för att skapa en bedömningsprofil.
1. Ange fälten för den nya bedömningsprofilen. Fälten motsvarar fälten på sidan **bedömningsprofiler** enligt beskrivningen i föregående avsnitt i denna artikel.

> [!NOTE]
> Profiler som skapas på sidan **Transportföretag** visas också på sidan **Bedömningsprofiler**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]