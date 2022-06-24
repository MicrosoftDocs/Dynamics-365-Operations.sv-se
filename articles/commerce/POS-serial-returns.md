---
title: Returserienummerkontrollerade produkter i kassan
description: I denna artikel beskrivs möjligheterna att validera serialiserade artiklar som en del av returprocessen i Microsoft Dynamics 365 Commerce-kassaprogrammet (POS).
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b2af301180dc2284400b887ce36357660bdd86fa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860331"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a>Returserienummerkontrollerade produkter i kassan

[!include [banner](includes/banner.md)]

I denna artikel beskrivs möjligheterna att validera serialiserade artiklar som en del av returprocessen i Microsoft Dynamics 365 Commerce-kassaprogrammet (POS).

> [!NOTE]
> I Commerce-versionen 10.0.20 och senare finns en ny funktion kallad **Enhetlig returbearbetningserfarenhet i kassan**. Om du vill använda serienummervalidering under returorderbearbetning i POS måste du aktivera funktionen. Mer information om andra funktioner som den här funktionen tillhandahåller när den aktiveras finns i [Skapa returer i kassan](POS-returns.md).
>
> När funktionen har aktiverats kan den inte stängas av.

## <a name="options-for-validating-serialized-returns"></a>Alternativ för validering av serialiserade returer

När funktionen **Bearbetningsupplevelse för enhetliga returer i kassan** är aktiverad kan organisationer validerar returer av serienummerkontrolelrade artiklar via kassan. Denna funktion kan varna användare om serienumret som returneras skiljer sig från det ursprungliga serienummer som såldes. I Commerce version 10.0.20 och senare är meddelandet som användarna får endast ett varningsmeddelande. Användarna kan fortsätta att bearbeta en retur mot ett serienummer som skiljer sig från serienumret som ursprungligen såldes.

Om du vill konfigurera serienummervalidering för en organisation efter det att funktionen **Upplevelsen för enhetlig returbearbetning i kassan** har aktiverats går du till **Butik och handel \> Administrationsinställning \> Parametrar \> Commerce-parametrar** i Commerce headquarters. På fliken **Lager**, på snabbfliken **Lagra lageråtgärder** anger du alternativet **Aktivera validering av serienummer för kassareturer** som **Ja**.

## <a name="process-returns-for-serialized-items-in-pos"></a>Bearbeta returer för serialiserade artiklar i kassan

Om alternativet **Aktivera validering av serienummer för kassareturer** har angetts som **Ja** kan användaren ange returens serienummer i informationsfönstret på sidan **Returnerbara produkter** när en serienummerkontrollerad artikel returneras via kassan. Om det angivna serienumret inte matchar det ursprungliga serienummer som såldes för försäljningstransaktionen får användaren ett varningsmeddelande. Programmet hindrar emellertid inte användaren från att fortsätta bokföra returen.

> [!NOTE]
> Kassa (POS) stöder för närvarande endast validering av serienummer på returrader där den ursprungliga beställda kvantiteten inte är större än ett. Om den ursprungliga försäljningsorderraden skapades i en icke-kassa-kanal, och om kvantiteten som beställts för den serialiserade artikeln på en given försäljningsrad är mer än ett, kan artikeln inte returneras korrekt via kassan.

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa returer i kassan](POS-returns.md)
