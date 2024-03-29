---
title: Konfigurera omvägar för steg i menyalternativ för mobila enheter
description: Denna artikel beskriver hur du konfigurerar omvägar för menyalternativ så att arbetare kan parkera den aktuella uppgiften, utföra en annan uppgift och sedan återgå till den ursprungliga uppgiften utan att förlora någon information.
author: Mirzaab
ms.date: 09/01/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour, WHSMobileAppFlowStepDetourSelectFields, WHSMobileAppFlowStepSelectPromotedFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2e387dd4e6499912f2d53dddc17ccc053f1ca699
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689321"
---
# <a name="configure-detours-for-steps-in-mobile-device-menu-items"></a>Konfigurera omvägar för steg i menyalternativ för mobila enheter

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 10.0.31 GA -->

> [!IMPORTANT]
> Funktionerna som beskrivs i denna artikel gäller bara den nya mobilappen Warehouse Management. De påverkar inte den gamla lagerställeappen, som nu har blivit inaktuell.

Denna artikel beskriver hur du konfigurerar omvägar för menyalternativ så att arbetare kan "parkera" den aktuella uppgiften, utföra en annan uppgift och sedan återgå till den ursprungliga uppgiften utan att förlora någon information.

En omväg är ett separat menyalternativ som kan öppnas från ett steg i en huvuduppgift. I slutet av omvägen returneras arbetaren till den plats där de lämnade huvuduppgiften. Under konfigurationen anger du det menyalternativ som ska fungera som en omväg. Du väljer också vilka fältvärden från huvuduppgiften som automatiskt ska vidarebefordras (kopieras) till omvägen och anges där. Därför måste du förstå var i uppgiftsflödet du vill att omvägen ska vara tillgänglig för arbetare. Du måste också se till att den information som måste kopieras till omvägen är tillgänglig för det steget i uppgiftsflödet.

## <a name="enable-detours-in-your-system"></a>Aktivera omvägar i systemet

Innan du kan konfigurera omvägar för steg i menyalternativ för mobila enheter måste du slutföra följande procedur för att aktivera de nödvändiga funktionerna och generera de obligatoriska fältnamnen i mobilappen Warehouse Management.

1. Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.
1. Se till att funktionen *Steginstruktioner för lagerställeapp* är aktiverad för systemet. Från och med version 10.0.29 av Supply Chain Management är denna funktion aktiverad som standard. Mer information om funktionen *Steginstruktioner för lagerställeapp* finns i [Anpassa stegtitlar och instruktioner för Warehouse Management-mobilappen](mobile-app-titles-instructions.md). Den här funktionen är en förutsättning för funktionen *Omvägar för lagerstyrningsapp*.
1. Aktivera följande funktioner, som innehåller de funktioner som beskrivs i den här artikeln:
    - *Omvägar för lagerstyrningsappen Warehouse Management*<br>(Från och med version 10.0.29 av Supply Chain Management är denna funktion aktiverad som standard.)
    - *Omvägar på flera nivåer för mobilappen Warehouse Management*
    - *Skicka omvägssteg automatiskt för Warehouse Management-mobilappen*
1. Om funktionen *Omvägar för appen Warehouse Management* och/eller *Omvägar på flera nivåer för mobilappen Warehouse Management* inte redan var aktiverad, uppdatera fältnamnen i mobilappen Warehouse Management genom att gå till **Warehouse management \> Inställningar \> Mobil enhet \> Namnordning för lagerställeapp** och välj **Skapa standardinställningar**. - Mer information finns i [Konfigurera fält för mobilappen för distributionslagerhantering](configure-app-field-names-priorities-warehouse.md).
1. Upprepa föregående steg för varje juridisk person (företag) där du använder mobilappen Warehouse Management.

## <a name="configure-a-detour-from-a-menu-specific-override"></a>Konfigurera en omväg från en menyspecifik åsidosättning

Gör på följande sätt när du vill konfigurera en omväg från en menyspecifik åsidosättning.

1. Skapa en menyspecifik åsidosättning för relevant meny och steg enligt beskrivningen i [Anpassa stegrubriker och instruktioner för Warehouse Management mobilapp](mobile-app-titles-instructions.md).
1. Hitta kombinationen av värden för **Steg-ID** och **Namn på menyalternativ** som du vill redigera, och välj sedan värdet i kolumnen **Steg-ID**.
1. På sidan som visas på snabbfliken **Tillgängliga omvägar (menyalternativ)** kan du ange det menyalternativ som ska fungera som en omväg. Du väljer också vilka fältvärden från huvuduppgiften som automatiskt ska kopieras till och från omvägen. Ett exempel på hur du använder dessa inställningar finns i scenariot senare i denna artikel.

## <a name="sample-scenario-1-sales-picking-where-a-location-inquiry-acts-as-a-detour"></a><a name="scenario-1"></a>Exempelscenario 1: Försäljningsplockning där en platsförfrågan fungerar som en omväg

I det här scenariot visas hur du konfigurerar en platsförfrågan som en omväg i ett arbetarstyrd försäljningsplockningsuppgiftsflöde. Den här omvägen kommer att göra det möjligt för medarbetare att slå upp all licens utan att upptäcka den plats de plockar från och plocka det ID-nummer de vill använda för att slutföra plockningen. Den här typen av omväg kan vara användbar om streckkoden skadas och därför inte kan läsas av skannerenheten. Alternativt kan det vara användbart om en arbetare måste lära sig vad som faktiskt finns i behållning i systemet. Observera att scenariot bara fungerar om du plockar från platser kontrollerade av ID-nummer.

### <a name="enable-sample-data"></a>Aktivera exempeldata

För att använda de angivna exempelposterna och värdena för att arbeta igenom det här scenariot måste du använda ett system där standard [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) är installerade. Du måste också välja den **USMF** juridiska personen innan du börjar.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-1"></a>Skapa en menyspecifik åsidosättning och konfigurera omvägen för scenario 1

I den här proceduren konfigurerar du en omväg för menyalternativet **Försäljningsplockning** i licenssteget.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Steg för mobil enhet**.
1. Sök efter steg-ID som kallas *LicensePlateId* och välj det.
1. Klicka på **Lägg till stegkonfiguration** i åtgärdsfönstret.
1. Använd fältet **Menyalternativ** i listrutan om du vill söka efter och välja *Försäljningsplockning*.
1. Välj **OK**.
1. Detaljsidan för åsidosättningen som du just skapat visas. På snabbflikarna **Tillgängliga omvägar (menyalternativ)**, välj **Lägg till** i verktygsfältet.
1. I dialogrutan **Lägg till omväg**, välj **Platsförfrågan** som omvägen som ska göras tillgänglig i Warehouse Management mobilapp.
1. Välj **OK**.
1. På snabbfliken **Tillgängliga omvägar (menyalternativ)** väljer du den omväg som du just lagt till och väljer sedan **Välj fält som ska skickas** i verktygsfältet.
1. I dialogrutan **Välj fält som ska skickas**, ange vilken information som ska skickas till och från omvägen. I det här scenariot gör du det möjligt för arbetare att använda platsen som de ska välja från som indata för omvägen för platsförfrågningen. I avsnittet **Skicka från försäljningsplockning**, välj **Lägga till** i verktygsfältet för att lägga till en rad i rutnätet. Ange sedan följande värden för den nya raden:

    - **Kopiera från försäljningsplockning:** *Plats*
    - **Klistra in platsförfrågan:** *plats*
    - **Skicka automatiskt:** *Vald* (sidan uppdateras med det tidigare värdet *Plats*)

1. Eftersom omvägen i det här scenariot är konfigurerad på ID-nummer-steget, kommer det att vara användbart om arbetare kan ta tillbaka ID-numret från förfrågan till huvudflödet. I avsnittet **Ta tillbaka från platsförfrågan**, välj **Lägga till** i verktygsfältet för att lägga till en rad i rutnätet. Ange sedan följande värden för den nya raden:

    - **Kopiera från platsförfrågan:** *ID-nummer*
    - **Klistra in i Försäljningsplockning:** *ID-nummmer*
    - **Skicka automatiskt:** *Rensat* (ingen automatisk uppdatering sker när du returnerar från omvägen med värdet *ID-nummer*)

1. Välj **OK**.

Omvägen är nu helt konfigurerad. En knapp för att starta omvägen för **Platsförfrågan** visas nu på steget för ID-nummer för menyalternativet **Försäljningsplockning**.

### <a name="complete-a-sales-pick-on-a-mobile-device-and-use-the-detour"></a>Slutföra en försäljningsplockning på en mobil enhet och använd omvägen

I den här proceduren slutför du en försäljningsplockning genom att använda Warehouse Management-mobilappen. Du använder den omväg som du just konfigurerat för att hitta det ID-nummer du kommer att använda för att slutföra plocksteget.

1. I Microsoft Dynamics 365 Supply Chain Management, skapa en försäljningsorder som kräver ett plocksteg för att plocka från en plats som spåras med ID-nummer. Släpp sedan försäljningsordern till lagret. Anteckna de arbets-ID som har genererats.
1. Öppna mobilappen för Warehouse Management och logga in på lagerställe 24. (I standarddemodata, logga in med *24* som användar-ID och *1* som lösenord.)
1. Välj menyn **Utgående** och välj sedan menyalternativet **Försäljningsplockning**.
1. Följ instruktionerna i dataposten på skärmen och ange det arbets-ID som genererades i steg 1.
1. Öppna åtgärdsmenyn i det steg som innehåller texten **Skanna ett ID-nummer**, öppna åtgärdsmenyn. Du bör se en ny knapp med etiketten **Platsförfrågan**. En pil i det övre vänstra hörnet visar att knappen startar en omväg. Välj **Platsförfrågan**.
1. Omvägen har startat. På nästa sida bekräftar du den plats som kopierats från huvudflödet.
1. I listan över tillgängliga ID-nummer på platsen kan du ange att du vill kopiera tillbaka till huvudflödet. Välj sedan knappen **Bakåt**.
1. Du returneras till huvudflödet för försäljningsplockning och licensinnehavaren har kopierats tillbaka till den från omvägen. Bekräfta värdet för att fortsätta till nästa steg.
1. Du kan nu fylla i resten av standardflödet genom att ange instruktionerna för den begärda datainmatningen.

Lagerställearbetet är nu slutfört. Arbetaren öppnar en omväg för att utföra en sekundär uppgift (platsförfrågan) utan att förlora sin plats i huvuduppgiften och tar med den information som krävs för att huvuduppgiften ska kunna slutföras.

## <a name="sample-scenario-2-item-inquiry-with-movement-and-adjustment-detours"></a>Exempelscenario 2: Artikelförfrågan med förflyttningar och justeringsomvägar

I det här scenariot visas hur du konfigurerar förflyttningar och justeringar som flera omvägar i platsförfrågans uppgiftsflöde. Den här kapaciteten kan vara användbar i situationer där en arbetare anländer till en plats, upptäcker att lagret på platsen skiljer sig från det som registrerats i systemet och därför måste justera eller flytta varor.

Du kan ersätta platsförfrågan med ett ID-nummer förfrågan eller en artikelförfrågan om det behövs.

### <a name="enable-sample-data"></a>Aktivera exempeldata

För att använda de angivna exempelposterna och värdena för att arbeta igenom det här scenariot måste du använda ett system där standard [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) är installerade. Du måste också välja den **USMF** juridiska personen innan du börjar.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-2"></a>Skapa en menyspecifik åsidosättning och konfigurera omvägen för scenario 2

I den här proceduren konfigurerar du en omväg för menyalternativet **Försäljningsplockning** i licenssteget.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Steg för mobil enhet**.
1. Sök och hitta steg-ID som kalla *LocationInquiryList*.

    > [!NOTE]
    > Om du vill använda en artikelförfrågan i stället för en platsförfrågan markerar du en rad där steg-ID:t får namnet *ItemInquiryList*. Om du vill använda en ID-nummer-förfrågan för kontoutgift, markerar du en rad där steg-ID:t kallas *LPInquiryList*.

1. Klicka på **Lägg till stegkonfiguration** i åtgärdsfönstret.
1. Använd fältet **Menyalternativ** i listrutan om du vill söka efter och välja *Platsförfrågan*.
1. Välj **OK**.
1. Detaljsidan för åsidosättningen som du just skapat visas. På snabbflikarna **Tillgängliga omvägar (menyalternativ)**, välj **Lägg till** i verktygsfältet.
1. I dialogrutan **Lägg till omväg**, välj **Rörelse** som omvägen som ska göras tillgänglig i Warehouse Management mobilapp.
1. Välj **OK**.
1. På snabbfliken **Tillgängliga omvägar (menyalternativ)** väljer du den omväg som du just lagt till och väljer sedan **Välj fält som ska skickas** i verktygsfältet.
1. I dialogrutan **Välj fält som ska skickas**, ange vilken information som ska skickas till och från omvägen. I det här scenariot förväntar du dig att medarbetarna letar efter ID-nummer-kontrollerade platser. Därför kan det vara användbart att kopiera ID-numret från förfrågan till omvägen **Rörelse**. I avsnittet **Skicka från försäljningsplockning**, välj **Lägga till** i verktygsfältet för att lägga till en rad i rutnätet. Ange sedan följande värden för den nya raden:

    - **Kopiera från platsförfrågan:** *plats*
    - **Klistra in rörelse:** *Loc / LP*
    - **Skicka automatiskt:** *Avmarkerat* (ingen automatisk uppdatering sker)

    I den här omvägen förväntar du dig inte att någon information ska kopieras tillbaka eftersom huvudflödet var en förfrågan där inga ytterligare steg krävs.

1. Välj **OK**.

Omvägen är nu helt konfigurerad. En knapp för att starta omvägen för **Rörelse** visas nu på steget för ID-nummer för menyalternativet **Platsförfrågan**.

### <a name="do-a-location-inquiry-on-a-mobile-device-and-use-the-detour"></a>Göra en platsförfrågan på en mobil enhet och använda omvägen

I den här proceduren vill du göra en platsförfrågan genom att använda Warehouse Management-mobilappen. Du använder sedan omvägen för att slutföra en rörelse av varor.

1. Öppna mobilappen för Warehouse Management och logga in på lagerställe 24. (I standarddemodata, logga in med *24* som användar-ID och *1* som lösenord.)
1. Välj menyn **Lager** och välj sedan menyalternativet **Platsförfrågan**.
1. Ange en plats som du vill fråga om, t.ex. *FL-001*.
1. När listan visas trycker du och håller ned ett av korten för att visa tillgängliga omvägar.
1. Välj **Rörelse**.
1. Observera att ID-numret har kopierats från kortet som du har valt. Bekräfta värdet.
1. Du kan nu följa standarduppgiftsflödet för att utföra rörelsen. När arbetet är klart öppnar du åtgärdsmenyn och väljer **Avbryt**.
1. Du går tillbaka till sidan **Platsförfrågan**. Observera att värdena inte uppdateras automatiskt. Därför måste du uppdatera sidan manuellt för att se ändringarna från förflyttningsvägen.

> [!NOTE]
> Med hjälp av funktionen *omvägar på flera nivåer i mobilapp Warehouse Management* kan du definiera omvägar på flera nivåer (omvägar inom omvägar), vilket innebär att medarbetare kan hoppa från en befintlig omleverans två en och sedan tillbaka igen. Funktionen har stöd för två nivåer av omvägar ut ur rutan och om det behövs kan du anpassa systemet till att stödja tre eller fler nivåer av omvägar genom att skapa kodtillägg i `WHSWorkUserSessionState` tabellen.
>
> Funktionen *Skicka omvägssteg automatiskt för Warehouse Management-mobilappen* kan göra det snabbare och enklare för arbetare att slutföra omvägsflöden i mobilappen Warehouse Management. Det gör det möjligt att hoppa över vissa flödessteg genom att låta appen fylla i omvägsdata på baksidan och sedan gå automatiskt till nästa steg genom att automatiskt skicka sidan, som visas i [*Exempelscenario 1: Försäljningsplockning där en platsförfrågan fungerar som en omväg*](#scenario-1).
