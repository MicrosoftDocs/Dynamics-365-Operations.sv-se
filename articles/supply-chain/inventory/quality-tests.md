---
title: Kvalitetshanteringstester
description: I denna artikel beskrivs hur du skapar tester som kan användas med kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
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
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac67ee97a4890c646daefa6b09feae25c4f15d0d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857617"
---
# <a name="quality-management-tests"></a>Kvalitetshanteringstester

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du skapar tester som kan användas med kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.

Du använder sidan **Tester** när du vill definiera och visa enskilda tester som fastställer huruvida dina produkter uppfyller kvalitetsspecifikationerna. Du kan tilldela en eller flera enskilda tester till en testgrupp. I detta fall anger du också testspecifik information, till exempel godtagbara måttvärden. Mätningsvärden används vid kvantitativa tester. För kvalitativa tester används testvariabler.

- För kvantitativa tester ställs fältet **Typ** in på *Heltal* eller *Del*. En måttenhet anges också. Kvalitetsspecifikationer och testresultat uttrycks som nummer.
- För kvalitativa tester måste du ange fältet **Typ** som *Alternativ*. Kvalitetstester kräver mer information om testvariabeln som mäts och dess fasta alternativ. Kvalitetsspecifikationer och testresultat uttryckts baserat på ett resultat.

Du kan som tillval också tilldela ett testinstrument till ett test. Testinstrumenten behövs emellertid inte för att skapa och använda tester med kvalitetsorder. Mer information finns i [Testinstrument för kvalitetshantering](quality-test-instruments.md).

Om du vill kan du även ange en enhet för ett test i syfte att ange måttenheten som testresultatet registreras i. Ett test för temperatur kan till exempel innehålla en enhet med antingen grader i Fahrenheit eller Celsius.

## <a name="example-of-a-test"></a>Exempel på ett test

Ett tillverkningsföretag utför två tester av inköpt material: ett kvantitativt test om materialkvalitet och ett kvalitativt test för förpackningsskador. Företaget anger ytterligare information om det kvalitativa testet för att definiera testvariabeln (exempelvis skadad förpackning) och dess utfall. Företaget använder sidan **Testgrupper** för att tilldela de två testerna till en testgrupp och ange testspecifik information. Testgruppen tilldelas en kvalitetsorder, så att företaget kan rapportera testresultaten för de två testerna.

## <a name="create-a-test"></a>Skapa test

Följ dessa steg om du vill skapa ett test.

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Tester**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Testgrupp** – Ange ett unikt ID eller namn för testgruppen.
    - **Beskrivning** – Ange en detaljerad beskrivning av testgruppen.
    - **Typ** – Välj den typ av resultat som testet resulterar i. För kvantitativa tester väljer du *Del* eller *Heltal*. Välj *Alternativ* för kvalitativa tester.
    - **Testinstrument** – Välj ett [testinstrument](quality-test-instruments.md) som ska användas för testet.
    - **Enhet** – Om du har valt *Del* eller *Heltal* i fältet **Typ** (det vill säga, om testet är ett kvantitativt) väljer du den måttenhet som testresultaten för registreras i.

1. Stäng sidan.

> [!NOTE]
> När du har sparat ett test kan du inte längre redigera fältet **Typ** i rutnätet. Om du måste ändra den typ av testresultat som ska registreras för ett test väljer du **Ändra kvalitetstesttyp** i åtgärdsfönstret. I dialogrutan **Ändra kvalitetstesttyp** anger du dältet **Ny typ** till önskad typ och väljer sedan **OK** för att stänga dialogrutan.

## <a name="additional-resources"></a>Ytterligare resurser

- [Testinstrument för kvalitetshantering](quality-test-instruments.md)
- [Testgrupper för kvalitetshantering](quality-test-groups.md)
- [Testvariabler för kvalitetshantering](quality-test-variables.md)
- [Kvalitetsassociationer](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
