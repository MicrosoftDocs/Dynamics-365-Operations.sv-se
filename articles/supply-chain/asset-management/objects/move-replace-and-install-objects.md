---
title: Flytta, ersätt och installera tillgångar
description: Det här avsnittet förklarar hur du flyttar, ersätter och installerar tillgångar i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectReplace, EntAssetObjectInstallLookup, EntAssetObjectMove, EntAssetObjectTableEditSubObjects
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 022ffc59b1b64913fedaf550f3fdb32141a94031
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020289"
---
# <a name="move-replace-and-install-assets"></a>Flytta, ersätt och installera tillgångar

[!include [banner](../../includes/banner.md)]

 

Det här avsnittet förklarar hur du flyttar, ersätter och installerar tillgångar i tillgångshantering. Du kan skapa enskilda tillgångar som inte har några relationer till andra tillgångar eller du kan skapa en tillgångsstruktur som innehåller en överordnad tillgång (tillgång på översta nivån) och relaterade underordnade tillgångar (undertillgångar). I tillgångshantering finns tre metoder för att flytta och ändra platsen för en tillgång:

- **Flytta** – Flytta en tillgång antingen till en annan tillgångsstruktur eller till en annan plats i samma tillgångsstruktur.
- **Ersätt** – ta tillfälligt bort en tillgång från en tillgångsstruktur så att den kan repareras eller renoveras och sedan lägga tillbaka den renoverade tillgången i tillgångsstrukturen senare. Du kan också permanent ersätta en begagnad tillgång med en ny tillgång.
- **Installera** – installera en överordnad tillgång och eventuella relaterade underordnade tillgångar på en funktionsplats.

> [!NOTE]
> Den tillgång som du flyttar, ersätter eller installerar kan relateras till en annan funktionsplats. I så fall kan tillgången använda ekonomiska dimensioner för den funktionsplatsen. På sidan **funktionsplatstyper** ställer du in hanteringen av ekonomiska dimensioner på funktionsplatser.

## <a name="move-asset"></a>Flytta tillgång

Använd funktionen **Flytta tillgång** för att flytta en tillgång antingen till en annan tillgångsstruktur eller till en annan plats i samma tillgångsstruktur. Du kan också flytta en tillgång från en tillgångsstruktur så att den blir en fristående tillgång som inte har några strukturrelationer.

> [!NOTE]
> Använd inte den här funktionen om tillgångarna repareras eller tillfälligt ersätts. Använd i stället funktionen **Ersätt tillgång** som beskrivs senare i det här avsnittet.

1. Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar** eller **Aktiva tillgångar**.
2. Välj tillgången som ska flyttas i listan. Om tillgången har underordnade tillgångar kan du också flytta dessa tillgångar.
3. Välj **Flytta tillgång**.
4. Om du vill flytta tillgången så att den blir en del av en tillgångsstruktur väljer du den nya överordnade tillgången i fältet **överordnad tillgång**. Om du flyttar en underordnad tillgång och du vill göra den till en fristående tillgång som inte har några strukturrelationer lämnar du fältet **överordnad tillgång** tomt.
5. Som standard är fältet **Giltighet** inställt på aktuellt datum och aktuell tid. Du kan dock välja ett annat datum och en annan tidpunkt som tillgångens flyttning är giltig från.
6. Välj **OK**.

## <a name="replace-asset"></a>Ersätt tillgång

Använd funktionen **Ersätt tillgång** i samband med reparationer, renovering eller permanent ersättning av en utsliten tillgång genom en ny tillgång. Den här funktionen används för att ersätta underordnade tillgångar i en tillgångsstruktur. För överordnade tillgångar (dvs. tillgångar som för närvarande inte har en överordnad tillgång), görs denna ersättning på en funktionsplats. Mer information om hur du ersätter överordnade tillgångar på en funktionsplats finns i [Installera tillgångar på funktionsplatser](../functional-locations/install-objects-on-functional-locations.md).

> [!NOTE]
> Om en reparationsverkstad är relaterad till din produktionsavdelning kan du skapa funktionsplatser som **reparation**, **kassation** och **lagring** för att hantera reparation och utbyte av tillgångar.

1. Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar** eller **Aktiva tillgångar**.
2. Välj den underordnade tillgången som ska bytas ut i listan. Om tillgången har underordnade tillgångar kan du också byta ut dessa tillgångar.
3. Välj **Ersätt tillgång**.

    I fältet **strukturändring** visas det senaste datumet och den tidpunkt då den valda tillgången och de relaterade underordnade tillgångarna flyttades till tillgångsstrukturen.

4. I avsnittet **Vald tillgång** i fältet **Målfunktionsplats** väljer du den funktionsplats som tillgången ska flyttas till. Välj till exempel platsen **reparera** eller **kassation**.

    I avsnittet **överordnad tillgång** visar fältet **Giltighet** det sista datum och tid som den överordnade tillgången och relaterade underordnade tillgångar har installerats eller flyttats på den aktuella funktionsplatsen.

5. I avsnittet **ny tillgång** i fältet **tillgång** väljer du tillgången som ska infogas som en temporär eller permanent ersättning för den valda tillgången. Den här tillgången kan för närvarande finnas på en annan funktionsplats, t.ex. **lagring**.
7. I avsnittet **Giltig från** anges fältet **Giltighet** som standard till aktuellt datum och aktuell tid. Du kan dock välja ett annat datum och en annan tidpunkt som tillgångens ersättning är giltig från.
8. Välj **OK**.

## <a name="install-asset"></a>Installera tillgång

Använd funktionen **installera tillgång** för att installera en tillgångsstruktur på en funktionsplats.

> [!NOTE]
> Välj alltid en överordnad tillgång. Överordnad tillgång och relaterade underordnade tillgångar kommer att flyttas till den valda funktionsplatsen.

1. Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar** eller **Aktiva tillgångar**.
2. I listan väljer du den överordnade tillgången som ska installeras på en annan funktionsplats.
3. Välj **Installera tillgång**.

    Avsnittet **Attribut** visar de tillgångsattribut som anges på den överordnade tillgången.

4. I fältet **Funktionsplats** väljer du den nya platsen.
5. Som standard är fältet **Giltighet** inställt på aktuellt datum och aktuell tid. Du kan dock välja ett annat datum och en annan tidpunkt som installationen på tillgångens struktur är giltig från.
6. Välj **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]