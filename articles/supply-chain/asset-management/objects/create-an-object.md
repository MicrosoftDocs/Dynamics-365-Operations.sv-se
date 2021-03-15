---
title: Skapa en tillgång
description: Det här avsnittet beskriver hur du skapar en tillgång i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTableCopyStructure, EntAssetObjectTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28c4685c3b6f543324953cd03646d5b15fdb8c59
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019439"
---
# <a name="create-an-asset"></a>Skapa en tillgång

[!include [banner](../../includes/banner.md)]

 

Det här avsnittet beskriver hur du skapar en tillgång i tillgångshantering.

1. Klicka på **tillgångshantering** > **allmänt** > **tillgångar** > **alla tillgångar** eller **aktiva tillgångar**.
2. Klicka på knappen **Nytt**.
3. I dialogrutan **skapa tillgångar** infogar du data om **tillgången** (tillgångs-ID) och tillgångens namn. Välj datum och tid för tillgången i fältet **Giltighet**. Från och med det datumet kan du installera tillgången på en funktionsplats samt flytta och ersätta tillgången i en tillgångsstruktur.
4. Välj tillgångstyp för tillgången (obligatoriskt fält) i fältet **tillgångstyp**. Om det behövs väljer du **tillgångstillverkare** och **tillgångsmodell** för tillgången. Om endast en produkt har ställts in, väljs den produkten automatiskt i fältet **tillgångstillverkare**. De val som är tillgängliga **tillgångstillverkare** och **tillgångsmodell** beror på inställningarna i [Tillgångstillverkare och-modeller](../setup-for-objects/product-and-model.md).
5. I gruppen **överordnad tillgång** är fältet **tillgång** tomt som standard. Om det behövs kan du välja en överordnad tillgång och sedan fylls alla fält i gruppen **överordnad tillgång** i automatiskt.
    >[!NOTE]  
    >När du väljer en överordnad tillgång är två eller tre flikar tillgängliga: fliken **mina tillgångar** innehåller tillgångar som är relaterade till de funktionsplatser som du (underhållsarbetaren som är inloggad på systemet) kan allokeras till. Om inga funktionsplatser ställs in för en underhållsarbetare i formuläret [underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md) kommer fliken **mina tillgångar** inte att visas. Fliken **aktiva tillgångar** innehåller en lista över alla tillgångar med livscykelstatus "aktiv". Fliken **tillgångsvisning** visar en trädvy över funktionsplatser och tillgångar som är installerade på dessa platser.

6. Den standardfunktionsplats som du har ställt in föreslås för tillgången i gruppen **tillgång** > fältet **> funktionsplats**. Välj en annan funktionsplats om det behövs.

    >[!NOTE]
    >När du har skapat en tillgång kan du installera den på en annan funktionsplats, om det behövs. Endast tillgångar på högsta nivån (tillgångar utan en aktuell överordnad tillgång) kan installeras på en funktionsplats. Det innebär att du installerar den översta nivån samt eventuella underordnade tillgångar på den valda funktionsplatsen. Läs mer om att installera tillgångar på funktionsplatser i [Introduktion till funktionsplatser](../functional-locations/introduction-to-functional-locations.md).

7. Klicka på **OK**.
8. Välj tillgången i listan **alla tillgångar** och klicka på knappen **redigera** för att lägga till ytterligare information till tillgången.

## <a name="general-information"></a>Allmän information

Den funktionsplats som tillgången är relaterad till visas i fältet **funktionsplats**. Om tillgången är en överordnad tillgång visas antalet underordnade som är relaterade till tillgången i fältet **underordnade**. Om tillgången är en underordnad tillgång till en befintlig tillgång visas ID för den överordnade tillgången i fältet **överordnad**.

Du kan redigera information om **tillgångstillverkare** och **tillgångsmodell** som används för att hantera reservdelar, alternativa reservdelar och standardvärden för jobbtyp. Se [tillgångstillverkare och modeller](../setup-for-objects/product-and-model.md) för mer information. Du kan också lägga till information om **Modellår** och **serienummer** om det behövs.

**Aktuellt livscykeltillstånd** används för att definiera om tillgången är aktiv eller inaktiv. När du skapar en tillgång är scenen alltid inställd på den första etappen i tillgångsfasgruppen. När du är redo att aktivera en tillgång klickar du på **uppdatera tillgångsstatus** och väljer det livscykeltillstånd som du har definierat som "tillgång aktiv" och klickar på **OK**.

**Obs!** när en tillgång är inställd på "inaktiv", är det inte längre möjligt att skapa arbetsorder för tillgången. Du kan inte heller schemalägga förebyggande underhållsjobb för en inaktiv tillgång.

Fälten **servicenivå** och **allvarlighetsgrad** relaterar till arbetsorder som skapats för tillgången. Fälten visar siffrorna **servicenivå** och **allvarlighetsgrad** som beräknats för den aktuella inställningen för tillgången. Referera till [tillgångsservicenivåer](../setup-for-objects/object-priorities.md) och [Allvarlighetsgradtyper för tillgång](../setup-for-objects/object-criticalities.md) när det gäller inställning av dessa värden.

## <a name="asset"></a>Tillgång

Du kan välja en **resurs** för tillgången. Resursvalet avgör vilken kalender som används för schemaläggning av arbetsorder. Resursval används ofta för anläggningstillgångar. Resurser och resursgrupper ställs in i **organisationsadministration** > **resurser** > **resursgrupper** eller **resurser**.

I fältet **anläggningstillgångsnummer** kan du välja en anläggningstillgång som ska relateras till tillgången. Detta är relevant om din tillgång är relaterad till ett investeringsprojekt.

- Om tillgången är kopplad till en anläggningstillgång kan du skapa en arbetsordertyp som ska användas för arbetsorder som är relaterade till ett investeringsprojekt. 
- Information om anläggningstillgångar för en tillgång är relaterad till modulen **anläggningstillgångar** i Dynamics 365 Supply Chain Management. Detta innebär att du **anläggningstillgångar** > **anläggningstillgångar** > **anläggningstillgångar** kan du få en översikt över tillgångshanteringsprojekt som kan relateras till en anläggningstillgång genom att välja tillgången i listan och visa innehållet i fönstret **Relaterad information** avsnittet > **associerade projekt**.


## <a name="details"></a>Detaljer

I fältet **aktiv från** visas det datum då du uppdaterade tillgångens livscykeltillstånd till ett aktivt tillstånd (referera till [tillgångens livscykeltillstånd](../setup-for-objects/object-stages.md) avseende inställning av livscykeltillstånd för tillgångar). Om tillgången inte längre är aktiv och du har uppdaterat tillgångens livscykeltillstånd till ett inaktivt livscykeltillstånd, visas det datum från vilket tillgången är inaktivt i fältet **aktiv till**. Vid behov kan du ändra dessa datum manuellt.

Om det behövs kan du infoga ett förväntat datum för ersättning av tillgången i fältet **ersättningsdatum**. Ett uppskattat värde för att ersätta tillgången kan infogas i fältet **ersättningsvärde**. Exempel: du kan använda ersättningsinformation för att jämföra den med kostnaderna för att underhålla en tillgång och sedan fatta ett beslut om att köpa en ny tillgång om underhållskostnaderna på den befintliga tillgången ökar snabbt.

## <a name="notes"></a>Anteckningar

Du kan lägga till noteringar som är relaterade till tillgången på snabbfliken **anteckningar**. Klicka på knappen **Lägg till tidsstämpel** innan du skriver anteckningen, om du vill lägga till användarinformation och ett datum/tidsstämpel i anteckningen.

## <a name="attributes"></a>Attribut

På den här snabbfliken kan du ange värden för tillgångsattribut. Dessa attribut kan användas för att beskriva egenskaper som är relevanta för tillgången, till exempel storlek, vikt eller maskinkonfiguration.

Klicka på **Lägg till rad** och välj attributtypen. Därefter infogar du **värdet** som är relaterat till attributtypen och sparar posten.

>[!NOTE] 
>Du kan få en översikt över tillgångsattributtyper och deras relation till tillgångarna i **tillgångsattribut** och **översikt över tillgångsattribut**. Se [översikt över tillgångsattribut](../objects/object-specification-overview.md) för mer information.

## <a name="vendor"></a>Leverantör

På snabbfliken **leverantör** väljer du ett leverantörskonto för tillgången. Om en leverantörsgaranti har beviljats kan du även infoga garantiinformation här.

## <a name="address"></a>Adress

På snabbfliken **adress** kan du infoga adressen till utrustningen. Om ingen adress infogas på tillgången, använder tillgången adressen till en överordnad tillgång, om den överordnade tillgången har en adress. Om ingen adress är relaterad till tillgången eller några överordnade i tillgångshierarkin, kan adressen till den funktionsplats där tillgången är installerad användas. Om den funktionsplatsen inte har en adress som är relaterad till den, används adressen till den överordnade funktionsplatsen på tillgången.

## <a name="asset-management-plans"></a>Planer för tillgångshantering

Underhållsplaner används för schemaläggning av förebyggande underhållsjobb med jämna mellanrum på tillgången. På den här snabbfliken kan du ställa in underhållsplanrader för den valda tillgången. Underhållsomgångar kan ställas in för olika tillgångar, där du måste utföra en liknande uppgift med jämna mellanrum. På fliken **underhållsplaner för funktionsplats** ser du de underhållsplaner som är relaterade till den funktionsplats där tillgången är installerad.

>[!NOTE]
>Om du tar bort en underhållsplanrad eller en underhållsrunda som är relaterad till en tillgång i **alla tillgångar** tar du också automatiskt bort alla underhållsscheman med status "skapad" som har skapats baserat på den underhållsplanen eller underhållsomgången.

## <a name="functional-location-maintenance-plans"></a>Underhållsplaner för funktionsplatser

På den här snabbfliken får du en översikt över underhållsplaner relaterade till den funktionsplats där tillgången är installerad.

## <a name="maintenance-rounds"></a>Underhållsomgångar

På den här snabbfliken kan du lägga till eller ta bort underhållsomgångar som är relaterade till tillgången.

## <a name="financial-dimensions"></a>Ekonomiska dimensioner

Du kan välja ekonomiska dimensioner för den tillgången.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]