---
title: Konfigurera e-postinställningar i Attract
description: I det här avsnittet beskrivs hur du konfigurerar inställningar för e-post som skickas av Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: e641e3f0d1873d91be1a1dc9bc22eb734a2b21d5
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124737"
---
# <a name="configure-email-settings-in-attract"></a>Konfigurera e-postinställningar i Attract

[!include [banner](includes/banner.md)]

Ditt varumärke etablerar förtroende och hjälper dig att skapa en relation med kandidater innan de ens kan användas för dina befattningar. Positiv varumärkesuppfattning attraherar de bästa talangerna och ökar lojaliteten för befintliga medarbetare. Microsoft Dynamics 365 Talent: Attract låter dig konfigurera e-postmeddelanden så att de avspeglar företagets varumärke. Därför kan du ge en konsekvent upplevelse för jobbsökande när de fortskrider genom ansökningsprocessen.

Med Attract kan du utföra följande åtgärder:

- Konfigurera e-postinställningar så att ditt företags konto för e-posttjänst i Microsoft Exchange används. På så sätt vet kandidater att e-postmeddelandena kommer från ditt företag. Du kan till exempel konfigurera dina inställningar så att sökande får e-postmeddelanden från `recruiting@contoso.com` i stället för `contoso@microsoft.com`.
- Skapa konsekvent profilering för alla e-postmeddelanden genom att ställa in globalt sidhuvud och sidfot för alla e-postmallar. 

> [!NOTE]
> Om du vill konfigurera Attract så att det använder ditt företags e-postkonto för att skicka e-post, behöver du tillägget för omfattande anställning.

## <a name="connect-an-email-service-account"></a>Anslut ett konto för e-posttjänst

Genom att ansluta företagets konto för e-posttjänst kan du skapa en varumärkesanpassad e-postupplevelse för dina jobbkandidater. Om du inte ansluter ditt företagskonto använder Attract Microsofts standardinställda varumärkesanpassade e-posttjänstkonto.

1. Välj **inställningar** (växelsymbol) i det övre högra hörnet och välj sedan **administratörscenter**.
2. På fliken **E-postinställningar** under **Konton för e-posttjänst**, välj **Anslut ett företagskonto**.

    ![Ansluta företagets konto hos e-posttjänsten i Attract](./media/attract-admin-email-service-accounts.png)

    Mer information om hur du skapar ett delat e-postkonto finns i [delade postlådor i Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).

3. Logga in i inloggningsfönstret i Microsoft med dina företagsreferenser.
4. Om du inte redan har skapat ett konto för e-posttjänsten, eller om du vill lägga till ett nytt väljer du **Lägg till nytt tjänstkonto** och anger sedan din e-postinformation. Om du redan har konfigurerat kontot för e-posttjänster som du vill använda väljer du det.

När kontot för e-posttjänst har konfigurerats visas det under **Konton för e-posttjänst**.

## <a name="disconnect-an-email-service-account"></a>Frånkoppla ett konto för e-posttjänst

Om du vill sluta att använda ditt företags domän i e-postkommunikationer genom Attract kan du koppla från ett konto för e-posttjänsten.

1. Välj **inställningar** (växelsymbol) i det övre högra hörnet och välj sedan **administratörscenter**.
2. På fliken **E-postinställningar**, under **Konton för e-postinställningar**, välj knappen **Mer** (tre vertikala punkter) under det konto för e-posttjänst som du vill frånkoppla.
3. Välj **frånkoppla e-postkonto**.

    ![Frånkoppla företagets konto hos e-posttjänsten](./media/attract-admin-disconnect-email-account.png)

4. Välj **Frånkoppla** när du uppmanas att bekräfta åtgärden.

    ![Bekräfta frånkoppling av företagets konto hos e-posttjänsten](./media/attract-admin-email-confirm-disconnect.png)

Om du inte ansluter ett annat konto för e-posttjänst kommer alla e-postmeddelanden som skickas från Attract att använda det varumärkesanpassade Microsoft e-posttjänstkonto som är standard.

## <a name="configure-email-template-settings"></a>Konfigurera inställningar för e-postmall

Du kan överföra en bild av företagets logotyp och annan information som ett anpassat sidhuvud för e-postmeddelanden. Du kan också ange länkar till din sekretesspolicy och användningsvillkor i e-postsidfötter.

> [!NOTE]
> Du måste följa tillämpliga lagar (bland annat gällande skräppost) i ditt land eller region och lagarna i landet eller regionen där e-postmottagaren finns. Dessa lagar omfattar regler om skräppost.

1. Välj **inställningar** (växelsymbol) i det övre högra hörnet och välj sedan **administratörscenter**.
2. På fliken **e-postinställningar** under **inställningar för e-postmall** drar du den bild som du vill använda som e-postrubrik till bildrutan, eller bläddrar till filen genom att klicka på bildrutan. Om du vill ersätta en befintlig bild måste du först markera **ta bort** bredvid den. Bilden måste vara en JPEG-, JPG-, PNG- eller SVG-fil. Den rekommenderade storleken för bilder är mellan 25 och 800 bildpunkter bred och mellan 25 och 150 pixlar hög. Den maximala filstorleken för rubriken är 1 MB.

    ![Lägga till en bild för företagets e-posthuvud](./media/attract-admin-email-header.png)

3. Under **Din sekretesspolicy för kommunikation**anger du en länk till företagets sekretesspolicy. Under **Ditt ditt företags användningsvillkor för kommunikation** ger en länk till ditt företags användningsvillkor.

    ![Lägga till länkar till företagets sekretesspolicy och användningsvillkor för e-postsidfoten](./media/attract-admin-email-footer.png)

4. Välj **Spara** om du vill spara dina inställningar för e-postmall.
