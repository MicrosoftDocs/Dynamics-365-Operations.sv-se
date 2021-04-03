---
title: Använd en relativ sökväg i databindningar för ER-modeller och -format
description: Med verktyget elektronisk rapportering kan du definiera elektroniska formatstrukturer och sedan beskriva hur strukturerna ska fyllas i.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 555e7c78dae85034bfcde417d8ac86bea5073d85
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565770"
---
# <a name="use-a-relative-path-in-data-bindings-of-er-models-and-formats"></a><span data-ttu-id="4010d-103">Använd en relativ sökväg i databindningar för ER-modeller och -format</span><span class="sxs-lookup"><span data-stu-id="4010d-103">Use a relative path in data bindings of ER models and formats</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4010d-104">Med verktyget elektronisk rapportering (ER) kan användarna definiera elektroniska formatstrukturer och sedan beskriva hur strukturerna ska fyllas med hjälp av data och algoritmer som finns i programmet.</span><span class="sxs-lookup"><span data-stu-id="4010d-104">The Electronic reporting (ER) tool lets users define electronic format structures and then describe how those structures should be filled by using data and algorithms that exist in the application.</span></span> <span data-ttu-id="4010d-105">Mer information finns i [Skapa konfigurationer för elektronisk rapportering (ER)](electronic-reporting-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="4010d-105">For more information, see [Create Electronic reporting (ER) configurations](electronic-reporting-configuration.md).</span></span> <span data-ttu-id="4010d-106">Om du vill ange dataflödet för att hämta Finance and Operations-data och använda det för att generera ett elektroniskt dokument måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="4010d-106">To specify the data flow for retrieving Finance and Operations data and using it to generate  an electronic document, you need to do the following:</span></span>

- <span data-ttu-id="4010d-107">Bind konfigurerade datakällor till element i den utformade domänbaserade [datamodellen](general-electronic-reporting.md#data-model-and-model-mapping-components).</span><span class="sxs-lookup"><span data-stu-id="4010d-107">Bind configured data sources to elements of the designed domain-specific [data model](general-electronic-reporting.md#data-model-and-model-mapping-components).</span></span> <span data-ttu-id="4010d-108">Modellstrukturen och de valda datakällorna kan ingå i en komplex hierarkisk struktur.</span><span class="sxs-lookup"><span data-stu-id="4010d-108">The model structure and selected data sources might be part of a complex hierarchical structure.</span></span> <span data-ttu-id="4010d-109">På grund av detta kan slutliga bindningar vara ganska stora och innehålla många element av olika typer (t.ex. relationer, register och metoder).</span><span class="sxs-lookup"><span data-stu-id="4010d-109">Because of this, final bindings can be quite large and contain many elements of different types (for example, relations, tables, and methods,).</span></span> <span data-ttu-id="4010d-110">Bindningarna kan bli mindre läsbara och ganska komplicerade att granska och förstå, särskilt inte för andra än ägare.</span><span class="sxs-lookup"><span data-stu-id="4010d-110">The bindings can become less readable and quite complex to review and understand, especially for non-owners.</span></span> 
- <span data-ttu-id="4010d-111">Bind datamodellelement med [formatkomponenter](general-electronic-reporting.md#FormatComponentOutbound) för att definiera vilka data som ska hämtas från datamodellen till det genererade formatets utdata.</span><span class="sxs-lookup"><span data-stu-id="4010d-111">Bind data model elements with [format](general-electronic-reporting.md#FormatComponentOutbound) components to define what data will be populated from the data model to the generated format’s output.</span></span>

<span data-ttu-id="4010d-112">För att förbättra användbarheten för ER-mappningar har funktionen för [relativa sökvägar](er-formula-language.md#relative-path) frigjorts.</span><span class="sxs-lookup"><span data-stu-id="4010d-112">To improve usability of ER mapping designers, the [relative path](er-formula-language.md#relative-path) feature has been released.</span></span> <span data-ttu-id="4010d-113">Som standard är alternativet för relativa sökvägar aktiverat för alla nya instanser av programmet där ER-designupplevelse är aktiverad (Microsoft Dynamics 365 Finance Microsoft Regulatory Configuration Service).</span><span class="sxs-lookup"><span data-stu-id="4010d-113">By default, the relative path representation option is turned on for any new instance of the application where ER design experience is enabled (Microsoft Dynamics 365 Finance, Microsoft Regulatory Configuration Service).</span></span> <span data-ttu-id="4010d-114">Vi har implementerat parametern för relativa sökvägar så att användarna kan fortsätta använda den fullständiga sökvägen när de arbetar med den här presentationen av ER-bindningar.</span><span class="sxs-lookup"><span data-stu-id="4010d-114">We implemented the relative path parameter so that users can keep using the full path when work with this presentation of ER bindings.</span></span>

<span data-ttu-id="4010d-115">[![Användarparametrar](./media/relative-path-01.png)](./media/relative-path-01.png)</span><span class="sxs-lookup"><span data-stu-id="4010d-115">[![User parameters](./media/relative-path-01.png)](./media/relative-path-01.png)</span></span>

 
<span data-ttu-id="4010d-116">När den relativa sökvägsanvändningsparametern aktiveras, ersätter ett enda @-tecken sökvägen till det överordnade objektet i bindningen för det aktuella modellelementet.</span><span class="sxs-lookup"><span data-stu-id="4010d-116">When the relative path usage parameter is turned on, a single @ character replaces the path to the parent item in the binding of the current model element.</span></span> <span data-ttu-id="4010d-117">Hela bindningssökvägen blir kortare, vilket gör hela mappningen tydligare och lättare att förstå.</span><span class="sxs-lookup"><span data-stu-id="4010d-117">The entire binding path becomes shorter, which makes the entire mapping more obvious and easier to understand.</span></span> <span data-ttu-id="4010d-118">I de flesta fall behövs ingen ytterligarebläddring i ER-designer för att du ska kunna visa alla bindningar för datamodellen.</span><span class="sxs-lookup"><span data-stu-id="4010d-118">In most cases, no additional scrolling is required in the ER designer to view all the bindings of the data model.</span></span>

<span data-ttu-id="4010d-119">[![Modellmappningsdesigner](./media/relative-path-02.png)](./media/relative-path-02.png)</span><span class="sxs-lookup"><span data-stu-id="4010d-119">[![Model mapping designer](./media/relative-path-02.png)](./media/relative-path-02.png)</span></span>
 
<span data-ttu-id="4010d-120">När du börjar utforma ett nytt ER-uttryck behöver du bara ange ett tecken för att definiera en bindning till ett fält i den överordnade artikeln.</span><span class="sxs-lookup"><span data-stu-id="4010d-120">When you start designing a new ER expression, you need to enter only one character to define a binding to a field of the parent item.</span></span>

<span data-ttu-id="4010d-121">[![Receptdesigner](./media/relative-path-03.png)](./media/relative-path-03.png)</span><span class="sxs-lookup"><span data-stu-id="4010d-121">[![Formula designer](./media/relative-path-03.png)](./media/relative-path-03.png)</span></span>
 
<span data-ttu-id="4010d-122">När du bestämmer dig för att ändra datakällan för den överordnade modellposten, med absolut sökvägsanvändning, måste du binda om den här modellartikeln manuellt, liksom alla kapslade objekt, till en ny datakälla.</span><span class="sxs-lookup"><span data-stu-id="4010d-122">When you decide to change the data source of the parent model item, with absolute path usage, you have to manually rebind this model item, as well as all nested items, to a new data source.</span></span> <span data-ttu-id="4010d-123">När relativ sökvägsanvändning är aktiverad och du väljer att en ny datakälla ska bindas till ett överordnat objekt, erbjuds du ett alternativ att automatiskt binda om alla kapslade element för det här överordnade objektet med ett klick.</span><span class="sxs-lookup"><span data-stu-id="4010d-123">When relative path usage is turned on, and you select a new data source to be bound to a parent item, you are offered an option to automatically rebind all nested elements of this parent item with one click.</span></span>

<span data-ttu-id="4010d-124">[![Ersätt befintligt sökvägsmeddelande](./media/relative-path-04.png)](./media/relative-path-04.png)</span><span class="sxs-lookup"><span data-stu-id="4010d-124">[![Replace existing path message](./media/relative-path-04.png)](./media/relative-path-04.png)</span></span>
 
<span data-ttu-id="4010d-125">Om du bekräftar ombindning av kapslade objekt kommer det nya överordnade objektet att placeras i sökvägen för varje kapslad post som innehåller den befintliga överordnade artikeln.</span><span class="sxs-lookup"><span data-stu-id="4010d-125">If you confirm rebinding of nested items, the new parent item will be placed to the path of each nested item containing the existing parent item.</span></span>
<span data-ttu-id="4010d-126">Den här funktionen avbryter inte kompatibiliteten i ER-ramverket.</span><span class="sxs-lookup"><span data-stu-id="4010d-126">This feature does not break the backward compatibility of the ER framework.</span></span> <span data-ttu-id="4010d-127">Alla tidigare utformade ER-konfigurationer fungerar med den här nya funktionen och inga uppgraderingar eller konverteringar krävs.</span><span class="sxs-lookup"><span data-stu-id="4010d-127">All previously designed ER configurations will work with this new feature, and no upgrades or conversions are required.</span></span>

> [!NOTE]
> <span data-ttu-id="4010d-128">Alla ändringar som införs genom massändring av bindningar för kapslade element i modellmappningar sparas korrekt i en konfigurations delta (spårning av ändringar).</span><span class="sxs-lookup"><span data-stu-id="4010d-128">All changes that are introduced by mass modification of bindings of nested elements in model mappings are correctly saved in a configuration delta (trace of changes).</span></span> <span data-ttu-id="4010d-129">På så sätt kan kunderna basera sin härledda version av modellmappningarna på en ny basversion av den som har ändrats med hjälp av den nya funktionen.</span><span class="sxs-lookup"><span data-stu-id="4010d-129">This allows customers to rebase their derived version of model mappings to any new base version of it that has been modified by using this new feature.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4010d-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4010d-130">Additional resources</span></span>

[<span data-ttu-id="4010d-131">ER-formelspråk</span><span class="sxs-lookup"><span data-stu-id="4010d-131">ER formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]