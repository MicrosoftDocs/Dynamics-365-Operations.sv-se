---
title: Bedömningsprofiler
description: I det här avsnittet beskrivs hur du ställer in data för bedömningsprofiler.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ceb2b7a5edcee6e248798a6bee114c7da7ecb18a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973970"
---
# <a name="rating-profiles"></a>Bedömningsprofiler

En bedömningsprofil påminner om ett logistik kontrakt (men inte ett juridiskt kontrakt). Den används för att bestämma transporttaxor för laster. 

Varje klassificeringsprofil är unik för ett transportföretag. I profilen kan du associera transportföretaget med ett tariffhuvud. Tariffmallen definierar tariffbastilldelning och tariffbasen. Tariffbasen bestämmer tariffen för transportföretaget.

Du kan ställa in en klassificeringsprofil med hjälp av generisk sida som visar en översikt över alla befintliga. Alternativt kan du ställa in klassificeringsprofilen direkt från transportföretaget. I båda fallen är informationen som du ställer in för värderingsprofilen densamma.

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a>Skapa eller redigera en bedömningsprofil på sidan värderingsprofiler

På sidan **bedömningsprofiler** kan du granska alla tillgängliga bedömningsprofiler. Du kan också redigera befintliga profiler och skapa nya profiler.

1. Gå till **Transporthantering \> Inställningar \> Bedömning \> Bedömningsprofil**.
1. I åtgärdsfönstret, välj **Ny** om du vill lägga till en ny bedömningsprofil i rutnätet eller välja **Redigera** för att redigera en befintlig profil.
1. Ange följande fält i raden för den nya eller befintliga bedömningsprofil:

    - **Bedömningsprofil** – Ange en unik identifierare (ID) för betygsprofilen.
    - **Namn** – Ange ett beskrivande namn för bedömningsprofilen.
    - **Transportföretag** – Välj ett transportföretag. Den bedömningsprofil som du ställer in visas också på sidan **Transportföretag** för det valda transportföretaget.
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
1. Ange fälten för den nya bedömningsprofilen. Fälten motsvarar fälten på sidan **bedömningsprofiler** enligt beskrivningen i föregående avsnitt i det här avsnittet.

> [!NOTE]
> Profiler som skapas på sidan **Transportföretag** visas också på sidan **Bedömningsprofiler**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]