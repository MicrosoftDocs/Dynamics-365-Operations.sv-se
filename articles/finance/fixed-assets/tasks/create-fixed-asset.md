---
title: Skapa en anläggningstillgång
description: I den här artikeln beskrivs hur du skapar en ny anläggningstillgångspost från listsidan för anläggningstillgångar.
author: moaamer
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00c72081d20015737aa027cee9474a54e498cef4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868501"
---
# <a name="create-a-fixed-asset"></a>Skapa en anläggningstillgång

[!include [banner](../../includes/banner.md)]

I den här artikeln beskrivs hur du skapar en ny anläggningstillgångspost från listsidan för **anläggningstillgångar**.

Systemet tilldelar tillgångsnumret baserat på den nummer serie som har tilldelats anläggningstillgångsgruppen. Om du använder mallen för anläggningstillgångar för att importera till gångar via Microsoft Excel-tillägget, eller om du använder ett annat importjobb, skapar systemet automatiskt anläggningstillgångsposter och ökar tillgångsnumret.

Om du vill skapa en tillgångspost manuellt följer du dessa steg.

1. Gå till **Navigeringsfönstret \> Moduler \> Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.
2. Klicka på **Ny** i **åtgärdsfönstret**.
3. Ange eller välj ett värde i fältet **Anläggningstillgångsgrupp.** Fältet **Nummer** får sin standard om du har aktiverat funktionen **Autonummer för anläggningstillgångar** i **Parametrar för anläggningstillgångar** och **Anläggningstillgångsgrupp**. Om inte måste du ange ett unikt nummer som identifierar anläggningstillgången.
4. I fältet **Namn** anger du ett värde. Ange ytterligare information som verksamheten kräver för tillgången.
5. Klicka på **Räkenskapsböcker** i **åtgärdsfönstret**.
6. Ange ett datum i fältet **Anskaffningsdatum.**
7. Ange ett tal i fältet **Anskaffningspris.**

    - Ange den ytterligare information som din verksamhet kräver för denna bok.
    - Ange den ytterligare information som verksamheten kräver för återstående böcker.

8. Stäng sidan.

Du kan även importera anläggningstillgångar genom att använda Excel-tillägget eller genom att köra ett importjobb från arbetsytan **Datahantering**. Innan du kör importen anger du värdena för de obligatoriska fälten i mallen.

Om du inte har definierat numret för anläggningstillgången i mallen för Excel-tillägget, eller i datahantering, skapar systemet ett anläggningstillgångsnummer för varje importerad tillgång och ökar nummer serien automatiskt för varje. Om du däremot importerar resurser och definierar tillgångsnummer i mallen ökar **inte** nummerserien automatiskt. I det här fallet kan en administratör behöva uppdatera nummerserien manuellt. Om du har definierat anläggningstillgångsnumret i mallen för Excel-tillägget använder systemet det definierade anläggningstillgångsnumret och ökar nummerserien.

> [!NOTE]                                                                                                         
> När avskrivningen har bokförts låses fälten **Satt i tjänst** och **Startdatum för avskrivning** på sidan **Bok**. Inget av fälten kommer att uppdateras från dataentiteten.

> [!WARNING]
> Anläggningstillgångsposten tas inte bort om transaktionerna bokfördes i den associerade boken, eller om den nya anläggningstillgången anges på en journalrad men inte bokförts. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
