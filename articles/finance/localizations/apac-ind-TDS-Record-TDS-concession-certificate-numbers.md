---
title: Registrera koncessionscertifikatnummer för TDS
description: I det här avsnittet beskrivs hur du registrerar koncessionscertifikatnumren för skatteavdrag vid källan (TDS) som har utfärdats till leverantörer.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: f543adc8bab5ca224bdb672d6b3c282c2d8531d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023586"
---
# <a name="record-tds-concession-certificate-numbers"></a><span data-ttu-id="34a7d-103">Registrera koncessionscertifikatnummer för TDS</span><span class="sxs-lookup"><span data-stu-id="34a7d-103">Record TDS concession certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34a7d-104">I det här avsnittet beskrivs hur du registrerar koncessionscertifikatnumren för skatteavdrag vid källan (TDS) som har utfärdats till leverantörer.</span><span class="sxs-lookup"><span data-stu-id="34a7d-104">This topic explains how to record the Tax Deducted at Source (TDS) concession certificate numbers that are issued to vendors.</span></span>

1. <span data-ttu-id="34a7d-105">Gå till **Skatt \> Indirekta skatter \> Källskatt \> Källskattekoncessioner**.</span><span class="sxs-lookup"><span data-stu-id="34a7d-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax concessions**.</span></span>
2. <span data-ttu-id="34a7d-106">I fältet **Skattetyp** väljer du **TDS** för att registrera koncessionscertifikat för TDS-skattetypen.</span><span class="sxs-lookup"><span data-stu-id="34a7d-106">In the **Tax type** field, select **TDS** to record concession certificates for the TDS tax type.</span></span>
3. <span data-ttu-id="34a7d-107">På fliken **Översikt** väljer du **Alt+N** för att skapa en rad.</span><span class="sxs-lookup"><span data-stu-id="34a7d-107">On the **Overview** tab, select **Alt+N** to create a line.</span></span>

    <span data-ttu-id="34a7d-108">[![Rubrik för den nya raden](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span><span class="sxs-lookup"><span data-stu-id="34a7d-108">[![Header of the new line](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span></span>

4. <span data-ttu-id="34a7d-109">I fältet **Källskattekod** väljer du den TDS-skattekod som leverantörens koncessionscertifikat utfärdas för.</span><span class="sxs-lookup"><span data-stu-id="34a7d-109">In the **Withholding tax code** field, select the TDS tax code that the vendor concession certificates are issued for.</span></span> <span data-ttu-id="34a7d-110">I fältet **Namn på källskattekod** visas namnet på TDS-skattekoden.</span><span class="sxs-lookup"><span data-stu-id="34a7d-110">The **Withholding tax code name** field shows the name of the TDS tax code.</span></span>
5. <span data-ttu-id="34a7d-111">I fälten **Från datum** och **Till datum** definierar du giltighetsperioden för det koncessionscertifikat som använder TDS-skattekoden för att beräkna TDS för leverantören på koncessionsbasis.</span><span class="sxs-lookup"><span data-stu-id="34a7d-111">In the **From date** and **To date** fields, define the period of validity for the concession certificate that uses the TDS tax code to calculate TDS for the vendor on a concessional basis.</span></span>
6. <span data-ttu-id="34a7d-112">I fältet **Anmärkningar** anger du eventuella anmärkningar.</span><span class="sxs-lookup"><span data-stu-id="34a7d-112">In the **Remarks** field, enter any remarks.</span></span>
7. <span data-ttu-id="34a7d-113">I fältet **Avsnitt** anger du den juridiska avsnittskod som TDS-koncessionscertifikatet visas under.</span><span class="sxs-lookup"><span data-stu-id="34a7d-113">In the **Section** field, enter the legal section code that the TDS concession certificate is availed under.</span></span>

    <span data-ttu-id="34a7d-114">Om avsnittskoden är 197 visas värdet "A" i kolumnen "Orsak till icke-avdrag/lägre avdrag" i formulär 26Q och kolumnen "Orsak till icke-avdrag/lägre avdrag/bruttoavdrag (i tillämpliga fall)", i formulär 27Q.</span><span class="sxs-lookup"><span data-stu-id="34a7d-114">If the section code is 197, the value "A" appears in both the "Reason for non-deduction/lower deduction" column in Form 26Q and the "Reason for non-deduction/lower deduction/grossing up (if any)" column in Form 27Q.</span></span> <span data-ttu-id="34a7d-115">Om avsnittskoden är 197A visas värdet "B" på båda ställena.</span><span class="sxs-lookup"><span data-stu-id="34a7d-115">If the section code is 197A, the value "B" appears in both those places.</span></span>

8. <span data-ttu-id="34a7d-116">Markera snabbfliken **Certifikat** om du vill registrera TDS-koncessionscertifikatnummer för leverantörer.</span><span class="sxs-lookup"><span data-stu-id="34a7d-116">Select the **Certificate** FastTab to record TDS concession certificate numbers for vendors.</span></span>
9. <span data-ttu-id="34a7d-117">I fältet **Leverantörskonto** väljer du det leverantörskonto som TDS-koncessionscertifikatet utfärdas för.</span><span class="sxs-lookup"><span data-stu-id="34a7d-117">In the **Vendor account** field, select the vendor account that the TDS concession certificate is issued for.</span></span>
10. <span data-ttu-id="34a7d-118">I fälten **Från datum** och **Till datum** definierar du giltighetsperioden för TDS-koncessionscertifikaten.</span><span class="sxs-lookup"><span data-stu-id="34a7d-118">In the **From date** and **To date** fields, define the period of validity for the TDS concession certificate.</span></span>

    <span data-ttu-id="34a7d-119">Beräkningen av TDS på koncessionsbasis baseras på perioden när certifikat skapas för leverantören.</span><span class="sxs-lookup"><span data-stu-id="34a7d-119">The calculation of TDS on a concessional basis is based on the period when the certificate is created for the vendor.</span></span>

11. <span data-ttu-id="34a7d-120">I fältet **Certifikat** anger du numret på TDS-koncessionscertifikatet.</span><span class="sxs-lookup"><span data-stu-id="34a7d-120">In the **Certificate** field, enter the TDS concession certificate number.</span></span>

    <span data-ttu-id="34a7d-121">[![Snabbfliken Certifikat](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span><span class="sxs-lookup"><span data-stu-id="34a7d-121">[![Certificate FastTab](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span></span>

12. <span data-ttu-id="34a7d-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34a7d-122">Close the page.</span></span>
