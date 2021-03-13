---
title: Felsöka produktinformation
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktinformation.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4c505ccfd1998acd40dbae715c7fa572e315af2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007526"
---
# <a name="troubleshoot-product-information"></a>Felsöka produktinformation

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktinformation.

## <a name="i-cant-delete-a-released-product"></a>Jag kan inte ta bort en frisläppt produkt.

### <a name="issue-description"></a>Problembeskrivning

Du kan bara ta bort en frisläppt produkt och alla dess varianter om den frisläppta produkten inte har några relaterade transaktioner.

### <a name="issue-resolution"></a>Problemlösning

Följ dessa steg för att ta bort en frisläppt produkt eller produktmall.

1. Stäng alla öppna transaktioner för artiklarna.
1. Minska lagret till 0 (noll).
1. Utför lagerstängning.
1. Radera alla produktvarianter för den produktmall som du vill ta bort.

## <a name="can-i-change-the-item-number-of-a-released-product"></a>Kan jag ändra artikelnumret för en frisläppt produkt?

I de flesta fall kan du inte redigera artikel nummer för frisläppta produkter, eftersom denna ändring medför att data skadas. Du kan bara redigera artikelnumret om du måste reparera skadade data som har orsakats av ett tidigare namnbyte på den släppta produktens primär nyckel, som nämnts i listan med [borttagna eller inaktuella funktioner för Finance and Operations 10.0.0 med plattformsuppdateringen 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).

Om du vill kunna redigera artikelnummer för släppta produkter [rösta på denna idé i idéportalen](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).

## <a name="the-default-flushing-principle-from-the-product-isnt-being-entered-on-the-bill-of-materials-line"></a>Standard avräkningsprincipen från produkten anges inte på strukturlisteraden.

### <a name="issue-description"></a>Problembeskrivning

När du lägger till en artikel på en strukturlisterad använder systemet inte standardinformationen för avräkningsprinciper som har ställts in för artikeln. Avräkningsprincipen från artikeln visas alltså inte på sidan **strukturrad**.

### <a name="issue-resolution"></a>Problemlösning

Om du anger en avräkningsprinciper på en strukturlisterad gäller den för strukturlisteraden. Om avräknings principen är tom, eller om den inte har angetts på en strukturlisterad, gäller emellertid den bokföringsprincip som har ställts in för artikeln även på den raden, även om den inte visas på strukturlisteraden.

Standardlogiken för andra funktioner i Microsoft Dynamics 365 Supply Chain Management fungerar vanligtvis inte på det här sättet. Däremot går det inte att ändra det aktuella beteendet. I annat fall kan en del befintliga anpassningar som är beroende av den brytas.

## <a name="the-system-lets-me-save-duplicate-bar-codes-for-different-items-or-for-the-same-item-that-has-different-dimensions"></a>I systemet kan jag spara dubbletter av streckkoder för olika artiklar eller för samma artikel med olika dimensioner.

Systemet upprätthåller för närvarande inte unika streckkoder och tillägget av denna begränsning skulle bli en icke-bakåtkompatibel ändring. Faktum är att Microsoft har belägg för att vissa befintliga kund installationer skulle brytas vid den här ändringen. Vi kommer dock att betrakta en bredare design ändring för att aktivera funktionen i framtiden.

## <a name="i-receive-the-following-error-message-when-i-edit-item-record-templates-the-warehouse-location-cannot-be-created-because-the-item-is-not-stocked-to-stock-items-the-stocked-product-option-on-the-associated-item-model-group-must-be-selected"></a>Följande felmeddelande visas när jag redigerar postmallar för artiklar: "det går inte att skapa lagerstället eftersom artikeln inte finns i lager. För lagerartiklar måste alternativet produkt i lager för den associerade artikel modellgruppen väljas".

### <a name="issue-description"></a>Problembeskrivning

Det här problemet uppstår om du gör följande för att skapa en mall för en artikel som inte finns i lager.

1. Öppna en frisläppt produkt som inte finns i lager.
1. I åtgärdsfönstret på fliken **Alternativ** välj **Postinformation**.
1. I dialogrutan **Postinformation** välj **Kontomall för företag**.

I det här fallet visas följande felmeddelande:

> Det går inte att skapa lagerstället eftersom artikeln inte finns i lager. För lagerartiklar måste alternativet produkt i lager för den associerade artikel modellgruppen väljas.

### <a name="issue-resolution"></a>Problemlösning

Processen för att skapa produktmallar kräver extra produktspecifika logik. Därför kan du inte använda allmänna knappen **mall för företagskonton** för det här syftet. Annars följer du dessa steg.

1. Öppna en frisläppt produkt.
1. I åtgärdsfönstret, på fliken **Produkt** i gruppen **Ny** markerar du sedan **Mall \> Skapa delad mall**.

## <a name="default-help-text-that-is-added-in-product-attributes-isnt-entered-in-a-released-product"></a>Standard hjälptext som läggs till i produktattribut anges inte i en frisläppt produkt.

En beskrivning och en hjälptext som läggs till i produktattribut visas eller anges inte som standard i de frisläppta produkterna. Detta beteende är av design.

## <a name="the-default-quantity-that-is-entered-differs-when-its-registered-from-a-bom-and-when-its-registered-from-a-bom-version"></a>Standardkvantiteten som anges skiljer sig när den registreras från en strukturlista och när den registreras från en strukturlisteversion.

### <a name="issue-description"></a>Problembeskrivning

När du lägger till en artikel i en strukturlista som standardkvantiteten till 1 i stället för den kvantitet som är definierad i fältet **min. orderkvantitet** på sidan **standard orderinställningar** för en vald produkt. När du lägger till en artikel från en strukturlisteversion, och artikeln och varianten väljs, tas emellertid den kvantitet som anges som standard med i beräkningen av den minsta kvantitet som anges i standard orderinställningarna för de specifika dimensionerna.

### <a name="issue-resolution"></a>Problemlösning

Detta är ett förväntat beteende. Men det faktum att logiken skiljer sig från strukturlistan och strukturlisteversionen är en känd utleverans. Det här beteendet ändras dock inte eftersom en ändring kan påverka många olika kundscenarier.

## <a name="in-the-released-product-details-i-cant-change-the-attached-images-that-were-uploaded-from-the-product-document-attachments-data-entity"></a>I den frisläppta produktinformationen kan jag inte ändra bifogade bilder som överförts från data enheten för bilagedata för produktdokument.

### <a name="issue-description"></a>Problembeskrivning

Det här problemet kan uppstå när en bild bifogas till ett objekt med hjälp av dataenheten *bilagedata för produktdokument*. I det här fallet visas artikelbilden för artikeln. Om du däremot väljer **ändra bild** visas ingenting i listan över överförda bilder. Dessutom visas inga bilagor för artikeln.

### <a name="issue-resolution"></a>Problemlösning

*EcoResProductDocumentAttachmentEntity* enheten (*bilagedata för produktdokument*) importerar dokument bilagor för *produkter* men inte för *frisläppta produkter*. (Frisläppta produkter kallas också *artiklar*.) Om du vill visa bilagor för en artikel på sidan **information om frisläppt produkt** måste du använda *EcoResReleasedProductDocumentAttachmentEntity* enhet (*Frisläppta bilagor till produktdokument*) istället.

## <a name="the-microsoft-flow-connector-shows-the-following-error-message-update-not-allowed-for-field-productnumber"></a>Microsoft Flow kopplingen visar följande felmeddelande: "uppdatering är inte tillåtet för fältet 'ProductNumber'."

### <a name="issue-description"></a>Problembeskrivning

Det här problemet uppstår om du försöker uppdatera fältet **produktnummer** med hjälp av *frisläppta produkter* enhet V2 och Microsoft Flow.

### <a name="issue-resolution"></a>Problemlösning

Detta är ett förväntat beteende. Möjligheten att redigera produktnumret för en frisläppt produkt togs bort i Dynamics 365 Finance and Operations 10.0.0 med plattformsuppdateringen 24 för att förhindra skadade data. I undantagsfall, där du måste reparera dataskadan som orsakades av ett tidigare namn på primärnyckeln till en släppt produkt, kan du be Microsoft Support att tillfälligt ta bort denna begränsning.

## <a name="i-cant-create-a-released-product-variant-in-another-legal-entity"></a>Jag kan inte skapa en frigiven produktvarianten i en annan juridisk person.

### <a name="issue-description"></a>Problembeskrivning

Om du försöker frisläppa en produktmall utan varianter och sedan skapar varianterna i varje juridisk person (företag) som de är nödvändiga kan du inte frisläppa varianterna med hjälp av variant-förslag. Du kan heller inte skapa varianterna manuellt.

### <a name="issue-resolution"></a>Problemlösning

Detta beteende är av design. Relationerna mellan en produktmall och de dimensioner som originalet kan ta hålls kvar på en delad nivå. Därför kan du inte skapa de tillgängliga dimensionerna för en delad produktmall i den specifika juridiska personen där dessa dimensioner släpps och sedan replikera processen i varje juridisk person där dimensionerna är obligatoriska. I stället måste du ändra versions processen för att kunna anpassa sig till den process som utformats.

Här är processen för att frisläppa produkter.

1. Skapa den delade produktmallen och de dimensioner som kan frisläppas till de juridiska enheterna.
1. Frisläpp produkterna till de juridiska personerna, antingen med hjälp av variantförslag eller genom att manuellt lägga till de kombinationer som ska frisläppas.

Alternativt kan du direkt skapa den frisläppta produkten.

## <a name="when-i-release-a-variant-in-another-company-i-receive-the-following-error-message-product-variant-with-specified-dimensions-has-already-been-created"></a>När jag släpper en variant i ett annat företag visas följande fel meddelande: "produktvarianten med angivna dimensioner har redan skapats."

### <a name="issue-description"></a>Problembeskrivning

Om en produktvarianten redan har frisläppts i ett företag A och du försöker frisläppa den i företag B genom att använda knappen **Ny** på sidan **frisläppta produktvarianter** visas följande felmeddelande:

> Produktvarianten med angivna dimensioner har redan skapats.

### <a name="issue-resolution"></a>Problemlösning

Knappen **Nytt** på sidan **frisläppta produktvarianter** skapar varianten och släpper den i företagets sammanhang. Om varianten redan har skapats kan du inte använda knappen **Ny** att frisläppa den i ett annat företag.

Du löser problemet genom att öppna sidan **produktmall** och välja **frisläppt produkt** för att frisläppa den befintliga varianten i det önskade företaget.
