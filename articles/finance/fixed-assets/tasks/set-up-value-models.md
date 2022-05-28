---
title: Ställ in värdemodeller
description: I den här proceduren visas hur du skapar en ny förteckning över anläggningstillgångar och kopplar den till en anläggningstillgångsgrupp.
author: moaamer
ms.date: 12/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71d256b600956a4e525cde626c958713f6258f5a
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727073"
---
# <a name="set-up-value-models"></a>Ställ in värdemodeller

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

I den här proceduren visas hur du skapar en ny förteckning över anläggningstillgångar och kopplar den till en anläggningstillgångsgrupp.

## <a name="create-a-book"></a>Skapa en räkenskapsbok
1. Gå till **Anläggningstillgångar \> Inställningar \> Böcker**.
2. Välj **Ny**.
3. I fältet **Boka** anger du ett värde.
4. I fältet **Beskrivning** anger du ett värde.
5. Ge alternativet **Beräkna avskrivning** värdet **Ja**.

    Om alternativet **Beräkna avskrivning** är inställt på **Ja** kommer den associerade tillgångsförteckningen att tas med i avskrivningsförslagen. Om den är inställd på **Nej**, kommer tillgångsförteckning skrivas av automatiskt.

6. I fältet **Avskrivningsprofil** ange eller välj ett värde.

    * En alternativ avskrivningsprofil kallas också för en omställningsmetod för avskrivning. Avskrivningsförslaget ställs om till denna profil när den alternativa profilen ska beräkna ett avskrivningsbelopp som är lika med eller högre än standardavskrivningsprofilen.
    * Den extraordinära avskrivningsprofilen används för ytterligare avskrivning av en tillgång i ovanliga omständigheter. Du kan till exempel använda det för att registrera den avskrivning på grund av naturkatastrofer.
    * Om du väljer **Skapa avskrivningsjusteringar med basjusteringar**, skapas avskrivningsjusteringar automatiskt när värdet på tillgången uppdateras. Annars påverkar det uppdaterade tillgångsvärdet endast framtida avskrivningsberäkningar.

7. Ange alternativet **Skapa avskrivningsjusteringar med basjusteringar** till **Ja**.

    * Som standard kommer transaktioner i förteckningar över anläggningstillgångar att bokföras i redovisningen. Du kan också avaktivera bokföring i redovisningen för boken genom att ange alternativet **Bokför i huvudboken** till **Nej**. Böcker som inte bokförs i redovisningen används som regel för momsrapporteringssyften. Detta alternativ ger dig mer flexibilitet att ta bort historiska transaktioner för tillgångsboken, detta eftersom transaktionerna inte har nedtecknats i redovisningen.
    * Som standard ställs fältet **Bokföringsskikt** in på **Aktuellt skikt** om boken bokförs i redovisningen och **Ingen** om boken inte bokförs i redovisningen. Uppdatera värdet för fältet **bokföringsskiktet** om du vill att transaktioner för denna räkenskapsbok bokförs till ett annat skikt.

8. Beräkna positiv avskrivning.

    * Som standard är alternativet **Beräkna positiv avskrivning** inställt på **Nej**. Den här inställningen anger att avskrivningen kommer att kreditera den valda tillgångsboken. Dessutom är både alternativet **Tillåt bokfört nettovärde högre än anskaffningspriset** och **Tillåt negativa bokförda nettovärden** till **Nej** och inställningarna kan ändras oberoende av varandra. 
    * För att beräkna positiv avskrivning ange alternativet **Beräkna positiv avskrivning** till **Ja**. Den här inställningen anger att avskrivningen kommer att debitera förteckning över anläggningstillgångar. När alternativet **Beräkna positiv avskrivning** är inställt på **Ja**, kommer alternativet **Tillåt bokfört nettovärde högre än anskaffningspriset** och **Tillåt negativa alternativ för bokfört nettovärde** automatiskt att ställas in på **Ja** och de låses. Det här låset hjälper till att säkerställa att positiv avskrivning endast tillämpas på anläggningstillgångar som förvärvats med negativt bokfört värde (kredit). 

10. Ange eller välj ett värde i fältet **Kalender**.

    Härledda böcker bokför transaktioner samtidigt till olika räkenskapsböcker. Du skapar transaktionerna med den primära räkenskapsboken, och under bokföringen bokförs en exakt kopia av transaktionen till den härledda räkenskapsboken. Ingen omberäkning med härledda boktransaktioner sker, så den ska inte användas för avskrivningstransaktioner.

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Associera räkenskapsboken till en anläggningstillgångsgrupp

1. Markera en **anläggningstillgångsgrupp**.
2. Ange eller välj ett värde i fältet **Anläggningstillgångsgrupp.**
3. I fältet **Tjänstelivstid**, ange ett tal.

    * Avskrivningsperioder beräknas efter det att tillgångens tjänstelivslängd har angetts.
    * Avskrivningspraxis kan anges efter vad som krävs i skattesyfte.
    * För anläggningstillgångar som är kopplade till leasingavtal åsidosätts värdet i fältet **Tjänstelivslängs** av det leasingvillkoret i tillgångsboken eller tillgångens livslängd (det av dem som är kortast). Om alternativet **Överföring av ägarskap** anges som **Ja** för leasingboken kommer värdet i fältet **Tjänstelivslängd** alltid att vara tillgångens livslängd.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
