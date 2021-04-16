---
title: Felsöka produktinformation
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktinformation.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a05e9957363ef6a659e25ceba84a168507cd641a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841537"
---
# <a name="troubleshoot-product-information"></a><span data-ttu-id="8ab8e-103">Felsöka produktinformation</span><span class="sxs-lookup"><span data-stu-id="8ab8e-103">Troubleshoot product information</span></span>

<span data-ttu-id="8ab8e-104">I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktinformation.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-104">This topic describes how to fix issues that you might encounter while you work with product information.</span></span>

## <a name="i-cant-delete-a-released-product"></a><span data-ttu-id="8ab8e-105">Jag kan inte ta bort en frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-105">I can't delete a released product.</span></span>

### <a name="issue-description"></a><span data-ttu-id="8ab8e-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-106">Issue description</span></span>

<span data-ttu-id="8ab8e-107">Du kan bara ta bort en frisläppt produkt och alla dess varianter om den frisläppta produkten inte har några relaterade transaktioner.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-107">You can delete a released product and all its variants only if the released product doesn't have any related transactions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8ab8e-108">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-108">Issue resolution</span></span>

<span data-ttu-id="8ab8e-109">Följ dessa steg för att ta bort en frisläppt produkt eller produktmall.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-109">Follow these steps to delete a released product or product master.</span></span>

1. <span data-ttu-id="8ab8e-110">Stäng alla öppna transaktioner för artiklarna.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-110">Close all open transactions for the items.</span></span>
1. <span data-ttu-id="8ab8e-111">Minska lagret till 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="8ab8e-111">Reduce the inventory to 0 (zero).</span></span>
1. <span data-ttu-id="8ab8e-112">Utför lagerstängning.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-112">Perform inventory closing.</span></span>
1. <span data-ttu-id="8ab8e-113">Radera alla produktvarianter för den produktmall som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-113">Delete all product variants for the product master that you want to delete.</span></span>

## <a name="can-i-change-the-item-number-of-a-released-product"></a><span data-ttu-id="8ab8e-114">Kan jag ändra artikelnumret för en frisläppt produkt?</span><span class="sxs-lookup"><span data-stu-id="8ab8e-114">Can I change the item number of a released product?</span></span>

<span data-ttu-id="8ab8e-115">I de flesta fall kan du inte redigera artikel nummer för frisläppta produkter, eftersom denna ändring medför att data skadas.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-115">In most cases, you can't edit item numbers for released products, because that change will cause data to become corrupted.</span></span> <span data-ttu-id="8ab8e-116">Du kan bara redigera artikelnumret om du måste reparera skadade data som har orsakats av ett tidigare namnbyte på den släppta produktens primär nyckel, som nämnts i listan med [borttagna eller inaktuella funktioner för Finance and Operations 10.0.0 med plattformsuppdateringen 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).</span><span class="sxs-lookup"><span data-stu-id="8ab8e-116">You can edit the item number only if you must repair data corruption that was caused by a previous rename of the primary key of that released product, as mentioned in the list of [removed or deprecated features for Finance and Operations 10.0.0 with Platform update 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).</span></span>

<span data-ttu-id="8ab8e-117">Om du vill kunna redigera artikelnummer för släppta produkter [rösta på denna idé i idéportalen](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).</span><span class="sxs-lookup"><span data-stu-id="8ab8e-117">If you want to be able to edit item numbers for released products, [vote for this idea in Ideas portal](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).</span></span>

## <a name="the-default-flushing-principle-from-the-product-isnt-being-entered-on-the-bill-of-materials-line"></a><span data-ttu-id="8ab8e-118">Standard avräkningsprincipen från produkten anges inte på strukturlisteraden.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-118">The default flushing principle from the product isn't being entered on the bill of materials line.</span></span>

### <a name="issue-description"></a><span data-ttu-id="8ab8e-119">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-119">Issue description</span></span>

<span data-ttu-id="8ab8e-120">När du lägger till en artikel på en strukturlisterad använder systemet inte standardinformationen för avräkningsprinciper som har ställts in för artikeln.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-120">When you add an item to a bill of materials (BOM) line, the system doesn't use the default flushing principle information that is set up for the item.</span></span> <span data-ttu-id="8ab8e-121">Avräkningsprincipen från artikeln visas alltså inte på sidan **strukturrad**.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-121">In other words, the flushing principle from the item doesn't appear on the **BOM line** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8ab8e-122">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-122">Issue resolution</span></span>

<span data-ttu-id="8ab8e-123">Om du anger en avräkningsprinciper på en strukturlisterad gäller den för strukturlisteraden.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-123">If you specify a flushing principle on a BOM line, it will apply to that BOM line.</span></span> <span data-ttu-id="8ab8e-124">Om avräknings principen är tom, eller om den inte har angetts på en strukturlisterad, gäller emellertid den bokföringsprincip som har ställts in för artikeln även på den raden, även om den inte visas på strukturlisteraden.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-124">However, if the flushing principle is blank, or if it isn't set on a BOM line, the flushing principle that is set on the item will still apply to that BOM line, even though it isn't shown on the BOM line.</span></span>

<span data-ttu-id="8ab8e-125">Standardlogiken för andra funktioner i Microsoft Dynamics 365 Supply Chain Management fungerar vanligtvis inte på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-125">The defaulting logic for other features in Microsoft Dynamics 365 Supply Chain Management doesn't usually work in this way.</span></span> <span data-ttu-id="8ab8e-126">Däremot går det inte att ändra det aktuella beteendet.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-126">However, the current behavior can't be changed.</span></span> <span data-ttu-id="8ab8e-127">I annat fall kan en del befintliga anpassningar som är beroende av den brytas.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-127">Otherwise, some existing customizations that rely on it might be broken.</span></span>

## <a name="the-system-lets-me-save-duplicate-bar-codes-for-different-items-or-for-the-same-item-that-has-different-dimensions"></a><span data-ttu-id="8ab8e-128">I systemet kan jag spara dubbletter av streckkoder för olika artiklar eller för samma artikel med olika dimensioner.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-128">The system lets me save duplicate bar codes for different items or for the same item that has different dimensions.</span></span>

<span data-ttu-id="8ab8e-129">Systemet upprätthåller för närvarande inte unika streckkoder och tillägget av denna begränsning skulle bli en icke-bakåtkompatibel ändring.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-129">The system doesn't currently enforce unique bar codes, and the addition of this restriction would be a breaking change.</span></span> <span data-ttu-id="8ab8e-130">Faktum är att Microsoft har belägg för att vissa befintliga kund installationer skulle brytas vid den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-130">In fact, Microsoft has evidence that some existing customer installations would be broken by this change.</span></span> <span data-ttu-id="8ab8e-131">Vi kommer dock att betrakta en bredare design ändring för att aktivera funktionen i framtiden.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-131">However, we will consider a broader design change to enable this feature in the future.</span></span>

## <a name="i-receive-the-following-error-message-when-i-edit-item-record-templates-the-warehouse-location-cannot-be-created-because-the-item-is-not-stocked-to-stock-items-the-stocked-product-option-on-the-associated-item-model-group-must-be-selected"></a><span data-ttu-id="8ab8e-132">Följande felmeddelande visas när jag redigerar postmallar för artiklar: "det går inte att skapa lagerstället eftersom artikeln inte finns i lager.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-132">I receive the following error message when I edit item record templates: "The warehouse location cannot be created because the item is not stocked.</span></span> <span data-ttu-id="8ab8e-133">För lagerartiklar måste alternativet produkt i lager för den associerade artikel modellgruppen väljas".</span><span class="sxs-lookup"><span data-stu-id="8ab8e-133">To stock items, the Stocked product option on the associated item model group must be selected."</span></span>

### <a name="issue-description"></a><span data-ttu-id="8ab8e-134">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-134">Issue description</span></span>

<span data-ttu-id="8ab8e-135">Det här problemet uppstår om du gör följande för att skapa en mall för en artikel som inte finns i lager.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-135">This issue occurs if you follow these steps to try to create a template for an item that isn't stocked.</span></span>

1. <span data-ttu-id="8ab8e-136">Öppna en frisläppt produkt som inte finns i lager.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-136">Open a released product that isn't stocked.</span></span>
1. <span data-ttu-id="8ab8e-137">I åtgärdsfönstret på fliken **Alternativ** välj **Postinformation**.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-137">On the Action Pane, on the **Options** tab, select **Record info**.</span></span>
1. <span data-ttu-id="8ab8e-138">I dialogrutan **Postinformation** välj **Kontomall för företag**.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-138">In the **Record information** dialog box, select **Company accounts template**.</span></span>

<span data-ttu-id="8ab8e-139">I det här fallet visas följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="8ab8e-139">In this case, you receive the following error message:</span></span>

> <span data-ttu-id="8ab8e-140">Det går inte att skapa lagerstället eftersom artikeln inte finns i lager.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-140">The warehouse location cannot be created because the item is not stocked.</span></span> <span data-ttu-id="8ab8e-141">För lagerartiklar måste alternativet produkt i lager för den associerade artikel modellgruppen väljas.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-141">To stock items, the Stocked product option on the associated item model group must be selected.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8ab8e-142">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-142">Issue resolution</span></span>

<span data-ttu-id="8ab8e-143">Processen för att skapa produktmallar kräver extra produktspecifika logik.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-143">The process of creating product templates requires extra product-specific logic.</span></span> <span data-ttu-id="8ab8e-144">Därför kan du inte använda allmänna knappen **mall för företagskonton** för det här syftet.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-144">Therefore, you can't use the generic **Company accounts template** button for this purpose.</span></span> <span data-ttu-id="8ab8e-145">Annars följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-145">Instead, follow these steps.</span></span>

1. <span data-ttu-id="8ab8e-146">Öppna en frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-146">Open a released product.</span></span>
1. <span data-ttu-id="8ab8e-147">I åtgärdsfönstret, på fliken **Produkt** i gruppen **Ny** markerar du sedan **Mall \> Skapa delad mall**.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-147">On the Action Pane, on the **Product** tab, in the **New** group, select **Template \> Create shared template**.</span></span>

## <a name="default-help-text-that-is-added-in-product-attributes-isnt-entered-in-a-released-product"></a><span data-ttu-id="8ab8e-148">Standard hjälptext som läggs till i produktattribut anges inte i en frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-148">Default Help text that is added in product attributes isn't entered in a released product.</span></span>

<span data-ttu-id="8ab8e-149">En beskrivning och en hjälptext som läggs till i produktattribut visas eller anges inte som standard i de frisläppta produkterna.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-149">A description and Help text that are added in the product attributes aren't visible or entered by default in the released products.</span></span> <span data-ttu-id="8ab8e-150">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-150">This behavior is by design.</span></span>

## <a name="the-default-quantity-that-is-entered-differs-when-its-registered-from-a-bom-and-when-its-registered-from-a-bom-version"></a><span data-ttu-id="8ab8e-151">Standardkvantiteten som anges skiljer sig när den registreras från en strukturlista och när den registreras från en strukturlisteversion.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-151">The default quantity that is entered differs when it's registered from a BOM and when it's registered from a BOM version.</span></span>

### <a name="issue-description"></a><span data-ttu-id="8ab8e-152">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-152">Issue description</span></span>

<span data-ttu-id="8ab8e-153">När du lägger till en artikel i en strukturlista som standardkvantiteten till 1 i stället för den kvantitet som är definierad i fältet **min. orderkvantitet** på sidan **standard orderinställningar** för en vald produkt.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-153">By default, when you add an item to a BOM, the quantity is set to 1 instead of the quantity that is defined in the **Min. order quantity** field on the **Default order settings** page for a selected product.</span></span> <span data-ttu-id="8ab8e-154">När du lägger till en artikel från en strukturlisteversion, och artikeln och varianten väljs, tas emellertid den kvantitet som anges som standard med i beräkningen av den minsta kvantitet som anges i standard orderinställningarna för de specifika dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-154">However, when you add an item from a BOM version, and the item and variant are selected, the quantity that is entered by default takes into account the minimum quantity that is set in the default order settings for the specific dimensions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8ab8e-155">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-155">Issue resolution</span></span>

<span data-ttu-id="8ab8e-156">Detta är ett förväntat beteende.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-156">This behavior is expected.</span></span> <span data-ttu-id="8ab8e-157">Men det faktum att logiken skiljer sig från strukturlistan och strukturlisteversionen är en känd utleverans.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-157">However, the fact that the logic differs in the BOM and the BOM version is a known issue.</span></span> <span data-ttu-id="8ab8e-158">Det här beteendet ändras dock inte eftersom en ändring kan påverka många olika kundscenarier.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-158">Nevertheless, this behavior won't be changed, because a change could affect many different customer scenarios.</span></span>

## <a name="in-the-released-product-details-i-cant-change-the-attached-images-that-were-uploaded-from-the-product-document-attachments-data-entity"></a><span data-ttu-id="8ab8e-159">I den frisläppta produktinformationen kan jag inte ändra bifogade bilder som överförts från data enheten för bilagedata för produktdokument.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-159">In the released product details, I can't change the attached images that were uploaded from the Product document attachments data entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="8ab8e-160">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-160">Issue description</span></span>

<span data-ttu-id="8ab8e-161">Det här problemet kan uppstå när en bild bifogas till ett objekt med hjälp av dataenheten *bilagedata för produktdokument*.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-161">This issue can occur when you attach an image to an item by using the *Product document attachments* data entity.</span></span> <span data-ttu-id="8ab8e-162">I det här fallet visas artikelbilden för artikeln.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-162">In this case, the item image is shown for the item.</span></span> <span data-ttu-id="8ab8e-163">Om du däremot väljer **ändra bild** visas ingenting i listan över överförda bilder.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-163">However, if you select **Change image**, nothing is shown in the list of uploaded images.</span></span> <span data-ttu-id="8ab8e-164">Dessutom visas inga bilagor för artikeln.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-164">Additionally, no attachments are shown for the item.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8ab8e-165">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-165">Issue resolution</span></span>

<span data-ttu-id="8ab8e-166">*EcoResProductDocumentAttachmentEntity* enheten (*bilagedata för produktdokument*) importerar dokument bilagor för *produkter* men inte för *frisläppta produkter*.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-166">The *EcoResProductDocumentAttachmentEntity* entity (*Product document attachments*) imports document attachments for *products* but not for *released products*.</span></span> <span data-ttu-id="8ab8e-167">(Frisläppta produkter kallas också *artiklar*.) Om du vill visa bilagor för en artikel på sidan **information om frisläppt produkt** måste du använda *EcoResReleasedProductDocumentAttachmentEntity* enhet (*Frisläppta bilagor till produktdokument*) istället.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-167">(Released products are also known as *items*.) To view the attachments for an item on the **Released product details** page, you must use the *EcoResReleasedProductDocumentAttachmentEntity* entity (*Released product document attachments*) instead.</span></span>

## <a name="the-microsoft-flow-connector-shows-the-following-error-message-update-not-allowed-for-field-productnumber"></a><span data-ttu-id="8ab8e-168">Microsoft Flow kopplingen visar följande felmeddelande: "uppdatering är inte tillåtet för fältet 'ProductNumber'."</span><span class="sxs-lookup"><span data-stu-id="8ab8e-168">The Microsoft Flow connector shows the following error message: "Update not allowed for field 'ProductNumber'."</span></span>

### <a name="issue-description"></a><span data-ttu-id="8ab8e-169">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-169">Issue description</span></span>

<span data-ttu-id="8ab8e-170">Det här problemet uppstår om du försöker uppdatera fältet **produktnummer** med hjälp av *frisläppta produkter* enhet V2 och Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-170">This issue occurs if you try to update the **Product number** field by using the *Released products* entity V2 and Microsoft Flow.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8ab8e-171">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-171">Issue resolution</span></span>

<span data-ttu-id="8ab8e-172">Detta är ett förväntat beteende.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-172">This behavior is expected.</span></span> <span data-ttu-id="8ab8e-173">Möjligheten att redigera produktnumret för en frisläppt produkt togs bort i Dynamics 365 Finance and Operations 10.0.0 med plattformsuppdateringen 24 för att förhindra skadade data.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-173">The ability to edit the product number for a released product was removed in Dynamics 365 Finance and Operations 10.0.0 with platform update 24 to help prevent data corruption.</span></span> <span data-ttu-id="8ab8e-174">I undantagsfall, där du måste reparera dataskadan som orsakades av ett tidigare namn på primärnyckeln till en släppt produkt, kan du be Microsoft Support att tillfälligt ta bort denna begränsning.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-174">In exceptional cases, where you must repair data corruption that was caused by a previous rename of the primary key of a released product, you can ask Microsoft Support to temporarily remove this restriction.</span></span>

## <a name="i-cant-create-a-released-product-variant-in-another-legal-entity"></a><span data-ttu-id="8ab8e-175">Jag kan inte skapa en frigiven produktvarianten i en annan juridisk person.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-175">I can't create a released product variant in another legal entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="8ab8e-176">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-176">Issue description</span></span>

<span data-ttu-id="8ab8e-177">Om du försöker frisläppa en produktmall utan varianter och sedan skapar varianterna i varje juridisk person (företag) som de är nödvändiga kan du inte frisläppa varianterna med hjälp av variant-förslag.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-177">If you try to release a product master without variants, and then create the variants in each legal entity (company) as they are required, you won't be able to release the variants by using variant suggestions.</span></span> <span data-ttu-id="8ab8e-178">Du kan heller inte skapa varianterna manuellt.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-178">You also won't be able to manually create the variants.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8ab8e-179">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-179">Issue resolution</span></span>

<span data-ttu-id="8ab8e-180">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-180">This behavior is by design.</span></span> <span data-ttu-id="8ab8e-181">Relationerna mellan en produktmall och de dimensioner som originalet kan ta hålls kvar på en delad nivå.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-181">The relations of a product master and the dimensions that the master can take are kept at a shared level.</span></span> <span data-ttu-id="8ab8e-182">Därför kan du inte skapa de tillgängliga dimensionerna för en delad produktmall i den specifika juridiska personen där dessa dimensioner släpps och sedan replikera processen i varje juridisk person där dimensionerna är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-182">Therefore, you can't create the available dimensions for a shared product master in the specific legal entity where those dimensions are released and then replicate the process in each legal entity where the dimensions are required.</span></span> <span data-ttu-id="8ab8e-183">I stället måste du ändra versions processen för att kunna anpassa sig till den process som utformats.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-183">Instead, you must change your release process to adapt to the designed process.</span></span>

<span data-ttu-id="8ab8e-184">Här är processen för att frisläppa produkter.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-184">Here is the process for releasing products.</span></span>

1. <span data-ttu-id="8ab8e-185">Skapa den delade produktmallen och de dimensioner som kan frisläppas till de juridiska enheterna.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-185">Create the shared product master and the dimensions that can be released to the legal entities.</span></span>
1. <span data-ttu-id="8ab8e-186">Frisläpp produkterna till de juridiska personerna, antingen med hjälp av variantförslag eller genom att manuellt lägga till de kombinationer som ska frisläppas.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-186">Release the products to the legal entities either by using variant suggestions or by manually adding the combinations that should be released.</span></span>

<span data-ttu-id="8ab8e-187">Alternativt kan du direkt skapa den frisläppta produkten.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-187">Alternatively, you can directly create the released product.</span></span>

## <a name="when-i-release-a-variant-in-another-company-i-receive-the-following-error-message-product-variant-with-specified-dimensions-has-already-been-created"></a><span data-ttu-id="8ab8e-188">När jag släpper en variant i ett annat företag visas följande fel meddelande: "produktvarianten med angivna dimensioner har redan skapats."</span><span class="sxs-lookup"><span data-stu-id="8ab8e-188">When I release a variant in another company, I receive the following error message: "Product variant with specified dimensions has already been created."</span></span>

### <a name="issue-description"></a><span data-ttu-id="8ab8e-189">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-189">Issue description</span></span>

<span data-ttu-id="8ab8e-190">Om en produktvarianten redan har frisläppts i ett företag A och du försöker frisläppa den i företag B genom att använda knappen **Ny** på sidan **frisläppta produktvarianter** visas följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="8ab8e-190">If a product variant has already been released in a company A, and you try to release it in company B by using the **New** button on the **Released product variants** page, you will receive the following error message:</span></span>

> <span data-ttu-id="8ab8e-191">Produktvarianten med angivna dimensioner har redan skapats.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-191">Product variant with specified dimensions has already been created.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8ab8e-192">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8ab8e-192">Issue resolution</span></span>

<span data-ttu-id="8ab8e-193">Knappen **Nytt** på sidan **frisläppta produktvarianter** skapar varianten och släpper den i företagets sammanhang.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-193">The **New** button on the **Released product variants** page creates the variant and releases it in the company context.</span></span> <span data-ttu-id="8ab8e-194">Om varianten redan har skapats kan du inte använda knappen **Ny** att frisläppa den i ett annat företag.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-194">If the variant has already been created, you can't use the **New** button to release it in another company.</span></span>

<span data-ttu-id="8ab8e-195">Du löser problemet genom att öppna sidan **produktmall** och välja **frisläppt produkt** för att frisläppa den befintliga varianten i det önskade företaget.</span><span class="sxs-lookup"><span data-stu-id="8ab8e-195">To fix the issue, open the **Product master** page, and select **Release product** to release the existing variant in the desired company.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]