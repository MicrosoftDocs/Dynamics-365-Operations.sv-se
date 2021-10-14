---
title: Kvalitetsorder
description: I detta ämne beskrivs hur du manuellt eller automatiskt skapar kvalitetsorder, samt hur du arbetar med dessa för att utföra granskningar och registrera testresultat i Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69a4a61a599f1279ec7ad68ebb20c7b4b0f37005
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571867"
---
# <a name="quality-orders"></a>Kvalitetsorder

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du manuellt eller automatiskt skapar kvalitetsorder, samt hur du arbetar med dessa för att utföra granskningar och registrera testresultat i Microsoft Dynamics 365 Supply Chain Management.

## <a name="automatically-created-quality-orders"></a>Automatiskt skapade kvalitetsorder

Du kan konfigurera systemet så att det automatiskt skapar kvalitetsorder baserat på regler för artikelstickprov. Mer information finns i [Artikelsampling för kvalitetshantering](quality-item-sampling.md).

## <a name="manually-create-quality-orders"></a><a name="manual-quality-orders"></a>Skapa kvalitetsorder manuellt

Gör så här om du vill skapa en kvalitetsorder manuellt:

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Kvalitetsorder**.
1. Välj **Ny**.
1. I dialogrutan **Kvalitetsorder**, i fältet **Referenstyp**, väljer du den lagerreferens som din kvalitetsorder ska relateras till. En beskrivning av referenstyperna som går att välja finns i avsnittet [Referenstyper för kvalitetsorder](#ref-types) längre fram i detta ämne.

    > [!NOTE]
    > Lager som är relaterat till den valda referensen måste vara tillgängliga. Om inget lager är tillgängligt för kombinationen av referenstyp, kvantitet och lagerdimensioner som du har valt, visas ett felmeddelande.

1. Gör något av följande, beroende på vilket värde du valt i fältet **Referenstyp**:

    - Om du har valt **Lager** krävs ingen ytterligare referensinformation.
    - Om du har valt **Försäljning** eller **Inköp** sak du ange följande information:

        - **Kontourval** – Referens till kund- eller leverantörsnumret.
        - **Referensnummer** – Referens till försäljningsordern eller inköpsordernumret.
        - **Referensparti** – Referens till den specifika försäljningsorderraden eller inköpsorderraden.

    - Om du har valt **Produktion**, **Karantän** eller **Samproduktframställning** anger du numret för produktions-, batch- eller karantänsorder i fältet **Referensnummer**.
    - Om du har valt **Flödesfunktion** anger du följande information:

        - **Referensnummer** – Referens till produktionsorder- eller batchordernumret.
        - **Funktionsnr.** – Referera till det specifika flödesfunktionensnumret.
        - **Funktion** – Referera till den specifika flödesfunktionen.
        - **Resurs** – Referens till den specifika resurs som måste användas med flödesfunktionen.

1. I fältet **Testgrupp** väljer du de tester som måste utföras.
1. I fältet **Kvantitet** anger du det antal artiklar som måste testas.
1. Ange eventuella ytterligare lagerdimensioner som krävs för den valda artikeln i avsnittet **Lagerdimensioner**.
1. Välj **OK**.

När en kvalitetsorder har skapats kan du börja inspektera lagret och registrera testresultaten. Mer information om hur du registrerar och validerar testresultat finns i [Kontrollera varornas kvalitet](tasks/inspect-quality-goods.md).

## <a name="quality-order-reference-types"></a><a name="ref-types"></a>Referenstyper för kvalitetsorder

Kvalitetsorder används för att spåra information om granskningar och testresultat för ett specifikt lager på lagerstället. En kvalitetsorder måste innehålla en referens som representerar källan till lagret som testas. Kvalitetsorder kan relateras till följande referenstyper:

- **Lager** – Denna referenstyp visar att du inspekterar tillgängligt lager. Granskningar av detta slag är vanligtvis slumpmässiga eller oplanerade, och utförs när en lagerarbetare identifierar ett problem.
- **Försäljning** – Denna referenstyp visar att du inspekterar lager som hör till en viss försäljningsorder. Granskningar av den här typen är vanligtvis kopplade till kundspecifikationer eller genereringen av ett analyscertifikat (CoA) som måste skickas till en kund som en del av en leverans. (Ett CoA kallas ibland även för efterlevnadscertifikat \[CoC\].)
- **Inköp** – Denna referenstyp visar att du inspekterar lager som hör till en inköpsorder. Granskningar av den här typen används ofta för att granska inkommande varor innan dess förs in i lager eller förbrukas i produktionsprocesser.
- **Produktion** – Denna referenstyp visar att du inspekterar lager som hör till en viss produktionsorder. Granskningar av den här typen används ofta för att inspektera färdiga varor innan dessa lagerförs.
- **Karantän** – Denna referenstyp visar att du inspekterar lager som hör till en viss karantänsorder. Karantänorder är en speciell typ av order som spårar lager på ett uppdelat lagerställe eller ett avskilt område i lagerstället. Granskningar av den här typen används ofta för att kontrollera varor som en kund har returnerat eller som har förts i karantän för vidare analys. Karantänorder kan genereras från kvalitetsorder. De kan också genereras från andra källor, och kvalitetsorder kan sedan relateras till karantänorder.
- **Flödesfunktion** – Denna referenstyp indikerar att du inspekterar lager som hör till ett visst flödessteg för en produktionsorder. Granskningar av den här typen används vanligtvis för att analysera pågående arbete (WIP) för en produkt innan detta går vidare till nästa steg i produktionsprocessen.
- **Samproduktframställning** – Denna referenstyp visar att du inspekterar lager som hör till en samprodukt för en produktionsorder. Granskningar av den här typen används vanligtvis för att kontrollera samprodukten från en batchorder innan samprodukten läggs till i lagret.

## <a name="view-and-create-quality-orders-from-various-parts-of-the-system"></a>Visa och skapa kvalitetsorder från olika delar av systemet

Kvalitetsorder kan skapas manuellt. De kan också skapas automatiskt baserat på de kvalitetsassociationer som du definierar. Mer information om hur du skapar och hanterar så att kvalitetsorder skapas automatiskt finns i [Kvalitetsassociationer](quality-associations.md).

På sidan för kvalitetsorder kan du skapa en ny kvalitetsorder manuellt, eller visa statusen för en kvalitetsorder som hör till en annan post. Det finns flera sätt att komma åt kvalitetsordersidan.

### <a name="from-the-quality-orders-page"></a>Från sidan Kvalitetsorder

Om du vill skapa kvalitetsorder manuellt och visa samtliga befintliga kvalitetsorder går du till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Kvalitetsorder**. Återstående avsnitt i detta ämne innehåller mer information om hur du arbetar med sidan **Kvalitetsorder**.

### <a name="from-sales-orders"></a>Från försäljningsorder

Om du vill arbeta med kvalitetsorder som hör till dina försäljningsorder går du till **Försäljnings- och marknadsföring \> Försäljningsorder \> Alla försäljningsorder** och följer något av följande steg:

- Öppna en försäljningsorder eller markera den i rutnätet. På fliken **Plocka och packa** i gruppen **Kvalitetshantering** i åtgärdsfönstret väljer du sedan **Kvalitetsorder** för att öppna sidan **Kvalitetsorder**. Där kan du visa, skapa eller uppdatera kvalitetsorder som hör till försäljningsordern.
- Öppna en försäljningsorder och markera sedan, på fliken **Rubrik**, snabbfliken **Allmänt**. I fältet **Status för kvalitetsorder** visas övergripande status för alla kvalitetsorder som hör till försäljningsordern.
- Öppna en försäljningsorder och markera sedan, på fliken **Rader**, snabbfliken **Försäljningsorderrader**. I kolumnen **Kvalitetsorderstatus** visas statusen för respektive rad i försäljningsordern.

### <a name="from-purchase-orders"></a>Från inköpsorder

Om du vill arbeta med kvalitetsorder som hör till dina inköpsorder går du till **Inköp och källor \> Inköpsorder \> Alla inköpsorder** och följer något av följande steg:

- Öppna en inköpsorder eller markera den i rutnätet. På fliken **Ta emot** i gruppen **Kvalitetshantering** i åtgärdsfönstret väljer du sedan **Kvalitetsorder** om du vill öppna sidan **Kvalitetsorder**. Du kan där visa, skapa eller uppdatera kvalitetsorder som hör till inköpsordern.
- Öppna en inköpsorder och markera sedan, på fliken **Rubrik**, snabbfliken **Allmänt**. I fältet **Status för kvalitetsorder** visas övergripande status för alla kvalitetsorder som hör till inköpsordern.
- Öppna en inköpsorder och markera sedan, på fliken **Rader**, snabbfliken **Inköpsorderrader**. I kolumnen **Kvalitetsorderstatus** visas statusen för respektive rad i inköpsordern.

### <a name="from-production-orders"></a>Från produktionsorder

Om du vill arbeta med kvalitetsorder som hör till dina produktionsorder går du till **Produktionsstyrning \> Produktionsorder \> Alla produktionsorder** och följer sedan något av följande steg:

- Öppna en produktionsorder eller markera den i rutnätet. På fliken **Visa**, i gruppen **Hantera kvalitet** i åtgärdsfönstret, väljer du **Kvalitetsorder** om du vill öppna sidan **Kvalitetsorder**. Du kan där visa, skapa eller uppdatera kvalitetsorder som hör till produktionsordern.
- Öppna en produktionsorder eller markera den i rutnätet. På fliken **Produktionsorder**, i gruppen **Produktionsinformation** i åtgärdsfönstret, väljer du **Flöde** för att öppna sidan **Produktionsflöde**. Om du vill visa kvalitetsorder som hör till en flödesfunktion gör du så här:

    - Välj målflödesfunktion i rutnätet. Välj sedan **Förfrågningar \> Kvalitetsorder** i åtgärdsfönstret.
    - Välj värdet i fältet **Funktionsnr.** om du vill att målflödesfunktionen ska öppna sin informationssida för **Produktionsflöde**. På snabbfliken **Allmänt** anger fältet **Kvalitetsorderstatus** statusen för de kvalitetsorder som hör till flödesoperationen.

- Öppna en produktionsorder och välj snabbfliken **Allmänt**. I fältet **Kvalitetsorderstatus** visas statusen för alla kvalitetsorder som hör till produktionsordern.

### <a name="from-quarantine-orders"></a>Från karantänorder

Om du vill arbeta med kvalitetsorder som hör till dina produktionsorder går du till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Karantänorder** och sedan följa något av följande steg:

- Granska värdena i kolumnen **Kvalitetsorderstatus**. På det här sättet kan du få veta den övergripande statusen för alla kvalitetsorder som är relaterade till respektive karantänorder i rutnät.
- Markera en karantänorder i rutnätet och välj sedan **Kvalitetsorder** i åtgärdsfältet för att visa, skapa eller uppdatera kvalitetsorder som är relaterade till karantänordern.

## <a name="advanced-actions-for-quality-orders"></a>Avancerade åtgärder för kvalitetsorder

Du kan utföra flera åtgärder på kvalitetsorder för att hantera status, skapa dokument och fråga om ytterligare information.

### <a name="reopen-a-quality-order"></a>Öppna kvalitetsorder på nytt

Som standard kan du inte längre redigera eller uppdatera en kvalitetsorder när denna har validerats och testerna har godkänts. I vissa fall kanske du måste öppna en kvalitetsorder på nytt efter det att den har slutförts.

Gör så här om du vill öppna en kvalitetsorder på nytt:

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Kvalitetsorder**.
1. Öppna den validerade kvalitetsordern eller markera den i rutnätet.
1. Välj **Öppna kvalitetsorder på nytt** i åtgärdsfönstret.

### <a name="create-a-certificate-of-analysis-for-a-quality-order"></a>Skapa ett analyscertifikat för en kvalitetsorder

Ett certifikat för analysrapport (CoA) är en rapport som genereras av en organisations kvalitetssäkringsteam. Den validerar att en produkt uppfyller särskilda bestämmelser eller krav. Dina kunder eller myndigheter på din plats kanske kräver certifikat för analysrapport. De kanske också krävs utifrån din bransch och den typ av produkter som du hanterar, köper, tillverkar eller säljer.

Med Supply Chain Management kan du generera ett certifikat för analysrapport från en kvalitetsorder. Rapporten innehåller resultaten av alla tester på kvalitetsordern där alternativet **Certifikat för analysrapport** som *Ja*. Detta alternativ kan ställas in som standard baserat på det test som du definierar på sidan **Test**. Du kan emellertid åsidosätta inställningen för specifika tester för en specifik kvalitetsorder.

Gör så här om du vill skapa ett analyscertifikat för kvalitetsorder:

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Kvalitetsorder**.
1. Välj den kvalitetsorder som du vill skapa ett analyscertifikat för.
1. I åtgärdsfältet väljer du **Förfrågningar \> Analyscertifikat**.
1. I åtgärdsfönstret på sidan **Analyscertifikat** väljer du **Ny**.
1. Optional: Välj den kontaktperson som intyget ska adresseras till i fältet **Kontakt**.
1. Välj **Skriv ut** i åtgärdsfönstret.
1. Definiera hur rapporten ska skrivas ut i dialogrutan **Analyscertifikat**. Välj sedan **OK** för att skriva ut rapporten på en skrivare, till skärmen, till en fil eller till e-post.
1. Stäng sidorna.

### <a name="block-or-unblock-inventory-for-a-quality-order"></a>Spärra eller ta bort spärr av lager för en kvalitetsorder

När en kvalitetsorder genereras automatiskt från en kvalitetsassociatering kan den artikelsampling som tilldelats kvalitetsassociateringen konfigureras i syfte att blockera den fullständiga lagerkvantiteten för den referens som testas. Mer information om artikelsampling finns i [Kvalitetshantering för artikelsampling](quality-item-sampling.md).

Om du inte använder fullständig spärr, eller om du skapar en kvalitetsorder manuellt, skapar systemet automatiskt en lagerspärrpost för kvantiteten av den artikel som testas på kvalitetsordern. I posten som skapas på sidan **Lagerspärr** anges fältet **Lagerspärrtyp** som *Kvalitetsorder*.

Om du vill visa och redigera lagerspärren för en kvalitetsorder som har valts på sidan **Lagerspärr** väljer du **Förfrågningar \> Lagerspärrar** i åtgärdsfönstret. Mer information sinns i [Lagerspärrar](inventory-blocking.md).

### <a name="inquire-about-the-details-of-a-quality-order"></a>Fråga om detaljer för en kvalitetsorder

Använd följande knappar i åtgärdsfönstret på sidan **Kvalitetsorder** om du vill visa mer information om eller relaterade till en kvalitetsorder:

- **Förfrågningar \> Arbetsdetaljer** – Öppna en sida där du kan visa lagerarbete relaterat till kvalitetsordern.
- **Förfrågningar \> Avvikelser** – Öppna en sida där du kan se alla avvikelser som är relaterade till kvalitetsordern.
- **Lager** – Kommandona på den här menyn är gemensamma för alla lagertransaktioner. Du kan använda dem för att visa eller uppdatera detaljer som transaktioner, lagerbehållning, reservationer och märkning.

### <a name="create-cases-related-to-quality-orders"></a>Skapa fall som hör till kvalitetsorder

Du kan skapa fall som hör till kvalitetsorder. På det här sättet kan du spåra detaljer om problem och arbeta med en lösning. Du kan sedan använda arbetsflödesfunktionerna i ärendehanteringen för att dirigera ett ärende genom en fördefinierad affärsprocess i syfte att få ytterligare godkännanden eller få mer information om ett visst problem. Du kan också använda kunskapsartiklar för att skapa en kunskapsbas med lösningar på vanliga problem.

## <a name="case-management-examples-for-quality-management"></a>Exempel på ärendehantering för kvalitetshantering

### <a name="example-1"></a>Exempel 1

Du arbetar för ett tillverkningsföretag som måste följa strikta regler för produktionen av reglerade produkter som exempelvis livsmedel. Kvalitetsorder används för att registrera och spåra detaljer om artiklarnas kvalitet under hela produktionsprocessen. Om en kvalitetsorder inte klarar specifika tester kan ett problem har uppstått med utrustningen. Fall används för att följa en affärsprocess och eskalera problemet till rätt tekniker, detta så att rotorsaken kan fastställas. För att göra affärsprocesser enklare att följa underhåller företaget en kunskapsbas över vanliga problem som rör kvalitetsorder och problem med utrustning.

### <a name="example-2"></a>Exempel 2

Du arbetar för ett distributionsföretag som levererar produkter som kan anpassas för olika länder och regioner. Vissa kunder har strikta specifikationer som måste följas. I annat fall kan avgifter och returer eller återbetalningar uppstå. Du använder kvalitetsorder när du vill spåra information om respektive test och resultat som matchar kundernas krav. Ärenden används för att granska och godkänna uppgifterna för äkthetscertifikat innan dokumentet genereras och bifogas tillsammans med annat leveransdokument.

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvalitetshanteringsprocesser](quality-management-processes.md)
- [Kvalitetstest](quality-tests.md)
- [Testgrupper för kvalitetshantering](quality-test-groups.md)
- [Kvalitetsassociationer](quality-associations.md)
- [Kvalitetshanteringsprocesser](quality-management-processes.md)
- [Aktivera kvalitets- och avvikelsehantering](enable-quality-management.md)
- [Kvalitetsstyrning för lagerprocesser](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
