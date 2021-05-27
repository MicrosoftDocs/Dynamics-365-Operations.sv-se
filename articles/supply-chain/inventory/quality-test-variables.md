---
title: Testvariabler för kvalitetshantering
description: I detta ämne beskrivs hur du skapar testvariabler som kan användas för kvalitativa tester på kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5102d09f5762a390d6fd3aadafcb2ed23820982
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021718"
---
# <a name="quality-management-test-variables"></a>Testvariabler för kvalitetshantering

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du skapar testvariabler som kan användas för kvalitativa tester på kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.

Du måste definiera en testvariabel och dess möjliga resultat för varje kvalitativt test som definieras på sidan **Tester**. (För kvalitativa tester är fältet **Typ** på sidan **Tester** inställt på *Alternativ*.)

Du använder sidan **Testvariabler** för att skapa, redigera och visa möjliga resultat för en testvariabel som hör till ett kvalitativt test. För varje resultat tilldelar du ett statusvärde som är antingen *Godkänd* eller *Misslyckades* för att ange huruvida testet har godkänts eller misslyckats när det resultatet har valts som ett testresultat. Du använder sidan **Testgrupper** om du vill tilldela en testvariabel och ett standardresultat för den till ett enskilt kvalitativt test.

För varje testvariabel rekommenderar vi att du definierar minst två resultat: ett som har statusvärdet *Godkänt* och ett som har resultatstatusen *Misslyckades*. Det finns ingen gräns för det totala antalet variabler eller resultat som kan definieras. Flera tester kan dessutom använda samma testvariabler för att registrera resultat.

## <a name="examples-of-test-variables"></a>Exempel på testvariabler

### <a name="example-1"></a>Exempel 1

Ett tillverkningsföretag utför två tester av tillverkade material. I ett test associeras pH-nivån med en färgremsa. Acceptabla pH-nivåer uppträder i ljusare färger, och oacceptabla pH-nivåer i mörkare färger. I ett annat test utförs flera visuella granskningar, och kvalitetsmedarbetare använder sitt omdöme för att fastställa huruvida artikeln klarar den visuella inspektionen eller inte.

### <a name="example-2"></a>Exempel 2

Ett tillverkningsföretag som tillverkar kakor använder ett inspektionstest för den färdiga produkten. Det här inspektionstestet har flera variabler. En variabel är smak, och de möjliga resultaten för denna är "god" eller "dålig". En andra variabel är färg, och de möjliga resultaten för denna är "alltför mörk", "alltför ljus" och "korrekt".

## <a name="create-a-test-variable"></a>Skapa en testvariabel

Gör så här om du vill skapa en testvariabel.

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Testvariabler**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Variabel** – Ange ett unikt ID eller namn för variabeln.
    - **Beskrivning** – Ange en detaljerad beskrivning av variabeln.

1. Med den nya raden fortsatt vald väljer du **Resultat** i åtgärdsfönstret.
1. På sidan **Testvariabelresultat** väljer du i åtgärdsfönstret **Ny** för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Resultat** – Ange ett unikt ID eller namn för resultatet.
    - **Beskrivning** – Ange en detaljerad beskrivning av resultatet.
    - **Resultatstatus** – Välj antingen *Godkänn* eller *Misslyckades* för att ange huruvida testet godkänts eller misslyckats när resultatet valts som testresultat.

1. Upprepa föregående steg för varje ytterligare resultat. Kontrollera att minst ett resultat har statusvärdet *Godkänt* och att minst ett har statusvärdet *Misslyckades*.
1. Stäng sidorna.

## <a name="additional-resources"></a>Ytterligare resurser

- [Testinstrument för kvalitetshantering](quality-test-instruments.md)
- [Kvalitetshanteringstester](quality-tests.md)
- [Testgrupper för kvalitetshantering](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
