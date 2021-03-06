---
title: Ställ in värdemodeller
description: I den här proceduren visas hur du skapar en ny förteckning över anläggningstillgångar och kopplar den till en anläggningstillgångsgrupp.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1131af52749854347fb92ec578e79ea601b93aed
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819588"
---
# <a name="set-up-value-models"></a>Ställ in värdemodeller

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar en ny förteckning över anläggningstillgångar och kopplar den till en anläggningstillgångsgrupp. Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen.


## <a name="create-a-book"></a>Skapa en räkenskapsbok
1. Gå till Anläggningstillgångar > Inställningar > Böcker.
2. Klicka på Ny.
3. Ange ett värde i fältet Book.
4. Ange ett värde i fältet Beskrivning.
    * När Calculate depreciation markeras kommer associerad räkenskapsbok att tas med i avskrivningsförslagen. Om räkenskapsboken inte markeras, skrivs den inte av automatiskt.  
5. Välj Yes i fältet Calculate depreciation field.
6. Ange eller välj ett värde i fältet Depreciation.
    * En alternativ avskrivningsprofil kallas också för en omställningsmetod för avskrivning. Avskrivningsförslaget ställs om till denna profil när den alternativa profilen ska beräkna ett avskrivningsbelopp som är lika med eller högre än standardavskrivningsprofilen.  
    * Den extraordinära avskrivningsprofilen används för ytterligare avskrivning av en tillgång i ovanliga omständigheter. Du kan till exempel använda det för att registrera den avskrivning på grund av naturkatastrofer.  
    * När Skapa avskrivningsjusteringar med basjusteringar markeras, skapas avskrivningsjusteringar automatiskt när värdet på tillgången uppdateras. Om det inte markeras, kommer det uppdaterade tillgångvärdet påverka endast avskrivningsberäkningar framåt.  
7. Välj Yes i fältet Create depreciation adjustments with basis adjustments field.
    * Som standard kommer transaktioner i förteckningar över anläggningstillgångar att bokföras i redovisningen. Du kan avaktivera bokföring i redovisningen för räkenskapsboken genom att ange fältet Post to general ledger som "No". Räkenskapsböcker som inte bokför i redovisningen används normalt för momsrapporteringssyften. Detta ger ytterligare när du vill ta bort historiska transaktioner för tillgångsförteckningen, detta eftersom de inte har förtecknats i redovisningen.  
    * Bokföringsskikt återgår till det aktuella lagret om räkenskapsboken bokför i redovisningen, eller inget (None) om den inte bokför i redovisningen. Uppdatera bokföringsskiktet om du vill att transaktioner för denna räkenskapsbok bokförs till ett annat skikt.  
8. Ange eller välj ett värde i fältet Kalender.
    * Härledda böcker bokför transaktioner samtidigt till olika räkenskapsböcker. Du skapar transaktionerna med den primära räkenskapsboken, och under bokföringen bokförs en exakt kopia av transaktionen till den härledda räkenskapsboken. Ingen omberäkning med härledda boktransaktioner sker, så den ska inte användas för avskrivningstransaktioner.  

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Associera räkenskapsboken till en anläggningstillgångsgrupp
1. Klicka på Anläggningstillgångsgrupper.
2. I fältet Anläggningstillgångsgrupp, ange eller välj ett värde.
3. I fältet Tjänstelivstid, ange ett tal.
    * Notera att avskrivningsperioderna beräknas efter det att du har angett tjänstelivslängden.  
    * Du kan ange avskrivningspraxis efter vad som krävs i skattesyfte.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]