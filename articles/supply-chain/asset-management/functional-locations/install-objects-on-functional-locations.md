---
title: Installera tillgångar på funktionsplatser
description: I det här avsnittet beskrivs hur du installerar tillgångar på en funktionsplats i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationObjectChange, EntAssetFunctionalLocationObjectInstall, EntAssetFunctionalLocationObject
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44e7d3f366ab79b54f021d01c69779ed04859be8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253648"
---
# <a name="install-assets-on-functional-locations"></a>Installera tillgångar på funktionsplatser

[!include [banner](../../includes/banner.md)]

 

När du har skapat funktionsplatsstrukturer är nästa steg att installera tillgångar på relevanta funktionsplatser. I det här avsnittet beskrivs hur du installerar tillgångar på dessa funktionsplatser i Tillgångshantering. Information om hur du skapar en tillgång finns i [Introduktion till tillgångar](../objects/introduction-to-objects.md).

Om du har skapat en tillgångsstruktur måste hela tillgångsstrukturen installeras på en funktionsplats. Därför kan endast överordnade tillgångar (tillgångar på toppnivå som inte har någon överordnad tillgång) väljas på en funktionsplats. Alla relaterade underordnade tillgångar (undertillgångar) kommer också att installeras på funktionsplatsen. När du installerar tillgångar på en funktionsplats, kan de ekonomiska dimensionerna för den funktionsplatsen automatiskt överföras till dem, beroende på inställningarna på den funktionsplatstyp som valts för den funktionsplatsen. För mer information om hur du ställer in funktionsplatstyper finns i [funktionsplatstyper](../setup-for-functional-locations/functional-location-types.md).

> [!NOTE]
> Du kan ställa in tillgångstyper på den funktionsplatstyp som används för en funktionsplats. I det här fallet när du installerar tillgångar på visas endast överordnade tillgångar som har samma typ av tillgång i listan över tillgångar som kan installeras på funktionsplatsen.

När du har installerat tillgångar på en funktionsplats kan du ersätta en överordnad tillgång eller en tillgångsstruktur som du behöver. Som när du installerar tillgångar, väljer du en överordnad tillgång som ska ersättas. Alla relaterade underordnade tillgångar kommer också att ersättas. 


## <a name="install-an-asset-structure-on-a-functional-location"></a>Installera en tillgångsstruktur på en funktionsplats.

1. Välj **tillgångshantering** \> **allmänt** \> **funktionsplatser** \> **alla funktionsplatser** eller **aktiva funktionsplatser**.
2. Välj den funktionsplats som tillgången ska installeras på.
3. Välj **Installera tillgång**.

    Avsnittet **attribut** visar en lista över tillgångsattributkrav som ställs in på den funktionsplatstyp som valts för den funktionsplatsen. Attributet är bara avsett för information. Systemet validerar inte attributen mot tillgångsattributen som ställs in på den tillgång som du installerar om. Du måste göra den verifieringen när du har valt en tillgång i fältet **tillgång**.

4. I fältet **tillgång** väljer du den överordnade tillgång som ska installeras. Alla relaterade underordnade tillgångar inkluderas automatiskt i installationen.

    Avsnittet **tillgångsattribut** till höger om tillgångslistan visar de tillgångsattribut som är relaterade till den valda tillgången.

5. I fältet **Giltighet** väljer du datum och tid då tillgångsinstallationen gäller från. Efter detta datum och tid kommer kostnaderna för tillgången och de relaterade undertillgångarna att relateras till den funktionsplatsen.

    > [!NOTE]
    > Tillgångsattributen som ställs in på tillgången läggs till i avsnittet **attribut**. Till exempel har attributkravet **vikt** lagts till som ett krav på både tillgången och funktionsplatsen. Om tillgången har attributkrav av samma typ som funktionsplatsen, anges värdena för tillgångens attributkrav i fältet **värde**. Därför kan du validera tillgångsvärden mot de attributkrav som ställs in på funktionsplatsen. Attributkraven som ställs in på funktionsplatsen markeras med en bockmarkering.

6. Välj **OK**.

    > [!NOTE]
    > Om du vill ändra installationen av en tillgång genom att installera den på en ny funktionsplats, följer du steg 1 till 6 i den här proceduren. När du installerar en tillgång på en ny funktionsplats, avinstalleras tillgången automatiskt från den tidigare funktionsplatsen. Alla aktiva underhållsbegäranden eller arbetsorder som har skapats på tillgången innan du installerade den på en ny funktionsplats överförs **inte** automatiskt till den nya funktionsplatsen. Om dessa underhållsbegäranden och arbetsorder fortfarande krävs för tillgången, måste du manuellt återskapa dem när tillgången har installerats på den nya platsen.

7. Om du vill visa en lista över alla tillgångar, inklusive undertillgångar, som är installerade på funktionsplatsen, väljer du den funktionsplatsen på sidan **alla funktionsplatser** och välj sedan **tillgångar**.
8. Om du vill visa en lista över aktiva underhållsbegäran, aktiva arbetsorder eller felregistreringar som är relaterade till de tillgångar som är installerade på en funktionsplats, väljer du den funktionsplatsen på sidan **alla funktionsplatser** och väljer sedan **begäran**, **arbetsorder** eller **fel**.

> [!NOTE]
> När tillgångsrelaterade data ändras uppdateras den automatiskt på den funktionsplats som tillgången är installerad på. Den här automatiska uppdateringen gäller ändringar av underhållbegäranden, arbetsorder, registreringar av tillgångsfel, registreringar av underhållsstopp och registreringar av tillgångsmått.

## <a name="automatically-create-one-asset-on-a-functional-location"></a>Skapa automatiskt en tillgång på en funktionsplats

Du kan ställa in funktionsplatsfaser och funktionsplatstyper för att hantera den automatiska skapandet av *en* tillgång på en funktionsplats. Tillgången får samma ID och namn som funktionsplatsen. Den här funktionen kan vara användbar när du hanterar underhåll på en stor, statisk tillgång, till exempel en byggnad.

Innan du kan skapa en tillgång automatiskt på en funktionsplats måste följande inställningsdata vara tillgängliga:

- Skapa en funktionsplatstyp för att hantera det automatiska skapandet av en tillgång. I fältet **tillgångstyp** väljer du en tillgångstyp. Mer information finns i [Funktionsplatstyper](../setup-for-functional-locations/functional-location-types.md).
- Skapa en funktionsplats livscykeltillstånd för att hantera det automatiska skapandet av en tillgång. Ange alternativet **Skapa tillgång** till **Ja**. Mer information finns i [livscykeltillstånd för funktionsplats](../setup-for-functional-locations/functional-location-stages.md).

När inställningsdata är tillgängliga är du redo att skapa en tillgång.

1. På sidan **alla funktionsplatser** kontrollerar du att den funktionsplats där du vill att tillgången ska skapas automatiskt använder den funktionsplatstyp som du skapade för detta ändamål.
2. Markera funktionsplatser i listan.
3. Välj **Uppdatera funktionsplatsens tillstånd** och välj sedan det livscykeltillstånd som du skapade för det här ändamålet. En tillgång installeras nu automatiskt på funktionsplatsen. Den här tillgången har samma namn som funktionsplatsen.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]