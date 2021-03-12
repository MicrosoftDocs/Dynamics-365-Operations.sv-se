---
title: Aktivera och konfigurera automatiska avgifter efter kanal
description: I det här avsnittet beskrivs hur du aktiverar och konfigurerar automatiska debiteringar utifrån kanal i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: d37b2b785dd29850dcd02d0905e5872445384990
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993738"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a>Aktivera och konfigurera automatiska avgifter efter kanal

I det här avsnittet beskrivs hur du aktiverar och konfigurerar automatiska avgifter utifrån kanal i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Du kanske har scenarier där återvinningsavgifter eller andra avgifter måste användas för en grupp produkter som säljs i alla eller vissa butiker i en viss delstat (t.ex. Kalifornien). Med funktionen **Aktivera filter för automatiska avgifter per kanal** i Commerce kan du ange automatiska debiteringar utifrån kanal (t.ex. en viss fysisk butikskanal). Den här funktionen finns i Dynamics 365 Commerce version 10.0.10 och senare.

Om du vill aktivera och konfigurera automatiska tillägg per kanal, måste du utföra följande uppgifter:

- Aktivera funktionen **aktivera filter för automatiska avgifter per kanal**.
- Konfigurera syftet med organisationshierarkin.
- Definiera automatiska tillägg per kanal.

> [!NOTE]
> Funktionen **aktivera filter för automatiska avgifter per kanal** fungerar bara om funktionen avancerade automatiska tillägg också är aktiverad. Information om hur du aktiverar funktionen avancerade automatiska tillägg finns i [Avancerade automatiska avgifter för flera kanaler](omni-auto-charges.md).

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a>Aktivera funktionen aktivera filter för automatiska avgifter per kanal

Om du vill aktivera automatiska debiteringar utifrån kanal i Commerce följer du stegen nedan.

1. Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.
1. På fliken **Inte aktiverad** i listan **Funktionsnamn** hitta och välj **aktivera filter för automatiska avgifter per kanal**.
1. Klicka på **Aktivera nu** i det nedre högra hörnet. När funktionen har aktiverats visas den i listan på fliken **alla**.
1. Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.
1. Hitta och välj i den vänstra rutan jobbet **1110** (**Global konfiguration**).
1. I åtgärdsfönstret väljer du **kör nu** om du vill sprida konfigurationsändringarna.

> [!WARNING]
> Om du inaktiverar funktionen **aktivera filter för automatiska avgifter per kanal** när du redan har använt den visas inte längre fältet **Butikskanalrelation** under **Automatiska avgifter** och du kommer då att förlora alla befintliga konfigurationer. Om du tar bort konfigurationerna för **Butikskanalrelation** kommer regler för automatiska avgifter att dubbleras och ett försök att inaktivera funktionen misslyckas. Innan du inaktiverar funktionen måste du granska alla automatiska tilläggsregler och göra nödvändiga ändringar.

## <a name="configure-the-organization-hierarchy-purpose"></a>Konfigurera syftet med organisationshierarkin

Ett nytt syfte för organisationshierarki med namnet **automatisk avgift för butik** har skapats för att hantera hierarkin för automatiska avgifter efter kanal.

Om du vill tilldela en standardhierarki till ett syfte för organisationshierarki i Commerce följer du dessa steg.
        
1. Gå till **Organisationsadministration \> Organisationer \> Syften med organisationshierarkier**.
1. I vänstra fönstret, välj **automatisk avgift för butik**.
1. Under **tilldelade hierarkier**, välj **Lägg till**.
1. I dialogrutan **organisationshierarkier** välj en organisationshierarki (till exempel **butiker efter region**) och välj sedan **OK**.
1. Under **tilldelade hierarkier**, välj **Ange som standard**.
1. Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.
1. Hitta och välj i den vänstra rutan jobbet **1040** (**produkter**).
1. I åtgärdsfönstret, klicka på **Kör nu**.
1. Upprepa de föregående två stegen för att köra jobben **1070** (**Kanalkonfiguration**) och **1110** (**Global konfiguration**).

![Konfiguration av syfte med organisationshierarkier för automatisk avgift för butik](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a>Definiera automatiska tillägg per kanal

När du har aktiverat funktionen **Aktivera filter för automatiska tillägg efter kanal** och konfigurerat syftet för organisationshierarkin **automatisk avgift för butik** kan du definiera automatiska avgifter per kanal på orderhuvudnivån eller orderradnivån.

Om du vill definiera automatiska debiteringar utifrån kanal i Commerce följer du stegen nedan.

1. Gå till **Kundreskontra \> Ställa in avgifter \> Automatiska avgifter**.
1. I vänstra fönstret i fältet **Nivå** välj antingen **Huvud** eller **Rad**, hitta och välj i den vänstra rutan.
1. I fältet **Butik kanalkod** välj lämplig kanalkod (t.ex. **Tabell** eller **Grupp**). Om standardinställningen **alla**, används tilläggsregler för alla kanaler.

    - Om du väljer **Grupp**, ska du se till att en avgiftsgrupp för butikskanaler **Retail och Commerce \> Kanalinställningen \> Avgifter \> Avgiftsgrupper för butikskanal**.
    - Om du väljer **Register** kan du välja en specifik kanal (t.ex. **San Francisco**) i fältet **Butikskanalrelation**.

1. Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.
1. Hitta och välj i den vänstra rutan jobbet **1040** (**produkter**).
1. I åtgärdsfönstret, klicka på **Kör nu**.
1. Upprepa de föregående två stegen för att köra jobben **1070** (**Kanalkonfiguration**) och **1110** (**Global konfiguration**).
    
![Automatiska tillägg definieras per kanal](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a>Exempelscenario

I följande exempel beskrivs de steg som krävs för att konfigurera en produkt så att återvinningsavgifter debiteras när produkten säljs via en San Francisco-kanal i en fysisk butik. Exemplet visar också hur de automatiska avgifterna visas i programmet Commerce-kassa (POS).

Organisationen definierar en avgiftskod som kallas **ÅTERVINNING**, som visas på bilden nedan.

![Avgiftskod för ÅTERVINNING](media/Auto-charges-charge-code.png)

En automatisk avgift skapas på radnivå. Det har följande konfigurationer:

- Fältet **Kontokod** ställs in på **Alla**.
- Fältet **Artikelkod** ställs in på **Register**.
- Fältet **Artikelrelation** ställs in på produkt-ID **91001**.
- Fältet **Kod för leveranssätt** ställs in på **Alla**.
- Fältet **Butikskanal** ställs in på **Register**.
- Fältet **butikskanalrelation** ställs in på **San Francisco**-butiken.

En rad för automatiska avgifter skapas. Det har följande konfigurationer:

- Fältet **Valuta** anges till **USD**.
- Fältet **Kod för avgifter** ställs in på **ÅTERVINNING**.
- Fältet **Kategori** ställs in på **fast**.
- Fältet **avgifter** anges till **$6,25**.

![Konfiguration av automatiska avgiften på radnivå och automatiska avgiftsraden](media/Auto-charges-recyclingfee-line-fee.png)

I kassaprogrammet skapas en försäljningsorder i **San Francisco** butikskanal. Raden **Avgifter** visar återvinningsavgiften på **$6,25**.

Genom att välja avgifter **Transaktionsalternativ \> Avgifter \> Hantera avgifter** i kassaprogrammet kan du se avgiftskoden och beskrivning för återvinningsavgiften.

![Återvinningsavgift i kassaprogrammet](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Avancerade automatiska avgifter för flera kanaler](omni-auto-charges.md)

[Allokera huvudavgifter för att matcha försäljningsrader](pro-rate-charges-matching-lines.md)
