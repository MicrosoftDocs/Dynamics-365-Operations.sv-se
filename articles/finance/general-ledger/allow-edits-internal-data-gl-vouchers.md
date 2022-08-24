---
title: Tillåt redigering av interna data i redovisningsverifikationer
description: I den här artikeln finns information om hur du redigerar interna data på redovisningsverifikationer.
author: kweekley
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 26fc6518f0b4eae815e047db1dbaadd7c56a2e67
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220676"
---
# <a name="allow-edits-to-internal-data-on-general-ledger-vouchers"></a>Tillåt redigering av interna data i redovisningsverifikationer

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]


När du bokför redovisningsposter i redovisningen används ofta fältet **Beskrivning** för att lagra interna noteringar eller dokumentation. Om informationen är felaktig kan den orsaka förvirring och göra det svårt att stänga perioden vid slut. Med den här funktionen kan redovisningschefen eller redovisningschefen åtgärda misstag genom att redigera fältet **Beskrivning** på bokförda verifikationer i redovisningen.

Ändringar i bokförda verifikationer i redovisningen begränsas till data som är interna. Med den här funktionen kan du aldrig redigera data som belopp, bokföringsdatum, redovisningskonton och transaktionsvaluta. Ändringar i dessa data påverkar den externa rapporteringen av bokslut och får endast göras med nya redovisningsverifikationer.

> [!NOTE]
> För Dynamics 365 Finance version 10.0.29 är den här funktionen begränsad till redigeringar i fältet **beskrivning**.

## <a name="edit-internal-data-on-general-ledger-vouchers"></a>Redigera interna data i redovisningsverifikationer

Innan interna data på huvudbokskuponger kan redigeras måste du aktivera **Tillåt redigering av interna data i redovisningsverifikationer** i arbetsytan **Funktionshantering**.
När funktionen har aktiverats måste den användare som redigerar bokförda verifikationer tilldelas rollen Redovisningschef eller Redovisningsansvarig. Du kan även lägga till behörigheter till andra roller genom att anpassa säkerhetsrollerna.

Redigeringsprocessen tillåts bara från sidan Verifikationstransaktioner.

1. Gå till **huvudboken** > **undersökningar och rapporter** > **verifikattransaktioner**.
2. Ange sökkriterier för att välja verifikationer i dialogrutan **SysQuery**.
3. Markera raderna för de verifikationer som du vill redigera och välj **Redigera verifikation** > **Redigera interna verifikationsdata**.

    [![Sida för Verifikationstransaktioner.](./media/voucher-transactions-page.png)](./media/voucher-transactions-page.png)
    
På sidan **Redigera interna verifikationsdata** visas följande data för varje rad som du har valt:
  
  - Redovisningskonto
  - Kontonamn
  - Verifikation
  - Aktuell beskrivning
  - Ny beskrivning

    [![Bokföringsorder.](./media/edit-internal-voucher-data.png)](./media/edit-internal-voucher-data.png)
    
> [!NOTE]
> Det är endast fältet **Ny beskrivning** som kan redigeras. Som standard matchar värdet i fältet **Aktuell beskrivning** så att du snabbt kan åtgärda mindre misstag i beskrivningen.

4. Ändra fältet **Ny beskrivning** på varje rad eller ta bort beskrivningen från varje rad.

   Du kan också göra så här om flera rader måste uppdateras med samma värde:

      1. Markera raderna som du vill redigera och markera sedan **Massuppdatera valda poster**.
      2. I fältet **Fält att redigera** väljer du fältet du vill redigera. För närvarande innehåller sökningen endast fältet **Ny beskrivning**.
      3. I fältet **Nytt värde** anger du en ny beskrivning.
      4. Välj **Uppdatera**. Alla markerade poster uppdateras med det nya värdet.

      [![Dialogrutan Massuppdatera de valda posterna.](./media/bulk-update-selected-records.png)](./media/bulk-update-selected-records.png)
    
5. I fältet **Orsak till redigering**, ange en anteckning för att förklara varför redigeringen gjordes. Noteringen visas på sidan **Redovisningsspårning för verifikationsredigeringar**.

   Flera redigeringar kan göras i samma verifikation och varje redigering spåras.

## <a name="audit-trail-of-voucher-edits"></a>Redovisningsspårning för verifikationsredigeringar

Redovisningsspår finns specifikt för att spåra de ändringar som görs med hjälp av den här funktionen. Du kan använda redovisningsspåret för verifikationsredigeringar på två sätt:

  - Gå till **huvudboken** > **undersökningar och rapporter** > **verifikattransaktioner**. På sidan **Verifikationsförfrågningar** välj **Redigera verifikation** > **Redovisningsspårning för verifikationsredigeringar**. Redovisningsspåret visas bara för den valda verifikationsposten. 
   
    Genom att öppna frågan på det här sättet kan du fokusera på alla redigeringar som gjorts till en enda verifikationspost.
  
  - Gå till **Redovisning** > **Periodiska uppgifter** > **Redovisningsspårning för verifikationsredigeringar**. Ange villkor för att ange verifikationerna som du vill visa redovisningsspåret för redigeringar för i dialogrutan. Om du vill visa redovisningsspåret för alla verifikationer låter du kriterierna vara tomma och väljer **OK**. 
    
    Genom att öppna förfrågan på det här sättet kan du filtrera efter redigeringar som gjorts på ett visst datum eller av en specifik användare.

På sidan **Redovisningsspårning för verifikationsredigeringar** visas följande information:

- **Skapat datum och tid** – Datumet och tiden för redigeringen.
- **Orsak till redigering** – Orsaken till att användaren angav redigeringen.
- **Skapad av** – Användaren som gjorde redigeringen.

Om du vill visa information om de olika redovisningsspåren går du nedåt till värdet **Skapades datum och klockslag**. Sidan **Visa redigerade verifikationsegenskaper** visar samma information som den ursprungliga redigeringssidan, inklusive den tidigare beskrivningen och den uppdaterade beskrivningen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
