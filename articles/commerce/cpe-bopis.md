---
title: Konfigurera BOPIS i en Dynamics 365 Commerce-utvärderingsmiljö
description: I det här avsnittet beskrivs hur du konfigurerar onlineköp, hämta i butik (BOPIS) i en Microsoft Dynamics 365 Commerce-utvärderingsmiljö efter att den har etablerats.
author: rubendel
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 62dabaa2610341cc8ad8e85812a317ac3123fcb1
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599806"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="61aea-103">Konfigurera BOPIS i en Dynamics 365 Commerce-utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="61aea-103">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="61aea-104">I det här avsnittet beskrivs hur du konfigurerar hämta i butik (BOPIS) i en Microsoft Dynamics 365 Commerce-utvärderingsmiljö efter att miljön har etablerats.</span><span class="sxs-lookup"><span data-stu-id="61aea-104">This topic explains how to configure buy online, pickup in store (BOPIS) in a Microsoft Dynamics 365 Commerce evaluation environment after the environment has been provisioned.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="61aea-105">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="61aea-105">Prerequisite</span></span>

<span data-ttu-id="61aea-106">Slutför procedurerna i det här avsnittet först när utvärderingsmiljö för Commerce har etablerats och konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="61aea-106">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned and configured.</span></span> <span data-ttu-id="61aea-107">Information om hur du etablerar och konfigurerar din miljö, se [Etablera en utvärderingsmiljö av Dynamics 365 Commerce](provisioning-guide.md) och [Konfigurera en utvärderingsmiljö av Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span><span class="sxs-lookup"><span data-stu-id="61aea-107">For information about how to provision and configure your environment, see [Provision a Dynamics 365 Commerce evaluation environment](provisioning-guide.md) and [Configure a Dynamics 365 Commerce evaluation environment](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span></span>

<span data-ttu-id="61aea-108">När hela Commerce-miljön har etablerats och konfigurerats kan du använda det här avsnittet för att aktivera BOPIS-scenarier.</span><span class="sxs-lookup"><span data-stu-id="61aea-108">After your Commerce environment has been provisioned and configured end to end, you can use this topic to enable BOPIS scenarios.</span></span>

## <a name="configure-the-pos"></a><span data-ttu-id="61aea-109">Konfigurera kassan</span><span class="sxs-lookup"><span data-stu-id="61aea-109">Configure the POS</span></span>

### <a name="configure-modern-pos"></a><span data-ttu-id="61aea-110">Konfigurera Modern POS</span><span class="sxs-lookup"><span data-stu-id="61aea-110">Configure Modern POS</span></span>

<span data-ttu-id="61aea-111">BOPIS-scenarier som involverar en kreditkortsbetalning kräver en maskinvarustation.</span><span class="sxs-lookup"><span data-stu-id="61aea-111">BOPIS scenarios that involve a credit card payment require a hardware station.</span></span> <span data-ttu-id="61aea-112">Maskinvarustationen ingår i Modern POS för Windows och Android-klienter.</span><span class="sxs-lookup"><span data-stu-id="61aea-112">The hardware station is built into Modern POS for Windows and Android clients.</span></span> <span data-ttu-id="61aea-113">Om du använder Cloud POS eller Modern POS för iOS måste kassan (POS) kombineras med en delad maskinvarustation.</span><span class="sxs-lookup"><span data-stu-id="61aea-113">If you're using Cloud POS or Modern POS for iOS, the point of sale (POS) client must be paired with a shared hardware station.</span></span> <span data-ttu-id="61aea-114">I det här avsnittet beskrivs hur du konfigurerar BOPIS för Windows och Android-klienter.</span><span class="sxs-lookup"><span data-stu-id="61aea-114">This topic explains how to configure BOPIS for Windows and Android clients.</span></span> <span data-ttu-id="61aea-115">Mer information om hur du konfigurerar en delad maskinvarustation finns i [Konfiguration och installation av Retail Hardware Station](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span><span class="sxs-lookup"><span data-stu-id="61aea-115">For information about how to set up a shared hardware station, see [Configure and install Retail hardware station](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span></span>

1. <span data-ttu-id="61aea-116">Gå till **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Kassor**.</span><span class="sxs-lookup"><span data-stu-id="61aea-116">Go to **Retail and Commerce \> Channel setup \> POS setup \> Registers**.</span></span>
2. <span data-ttu-id="61aea-117">Välj kassa **SANFRAN-5**och välj sedan **redigera**.</span><span class="sxs-lookup"><span data-stu-id="61aea-117">Select register **SANFRAN-5**, and then select **Edit**.</span></span>
3. <span data-ttu-id="61aea-118">Ändra värdet för fältet **Maskinvaruprofil** från **HW002** till **HW001** och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="61aea-118">Change the value of the **Hardware profile** field from **HW002** to **HW001**, and then select **Save**.</span></span>
4. <span data-ttu-id="61aea-119">För att synkronisera ändringarna, gå till **Retail och Commerce \> Retail och Commerce IT \> Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="61aea-119">To synchronize the changes, go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
5. <span data-ttu-id="61aea-120">Välj distributionsschema **1090** och sedan på åtgärdsfönstret väljer du **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="61aea-120">Select distribution schedule **1090**, and then, on the Action Pane, select **Run now**.</span></span>
6. <span data-ttu-id="61aea-121">Välj **ja** och sedan **OK** för att initiera datasynkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="61aea-121">Select **Yes** and then **OK** to initiate data synchronization.</span></span> 

### <a name="install-modern-pos"></a><span data-ttu-id="61aea-122">Installera Modern POS</span><span class="sxs-lookup"><span data-stu-id="61aea-122">Install Modern POS</span></span>

1. <span data-ttu-id="61aea-123">Gå till **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Enheter**.</span><span class="sxs-lookup"><span data-stu-id="61aea-123">Go to **Retail and Commerce \> Channel setup \> POS setup \> Devices**.</span></span>
2. <span data-ttu-id="61aea-124">Välj enhet **SANFRANCIS-5**.</span><span class="sxs-lookup"><span data-stu-id="61aea-124">Select device **SANFRANCIS-5**.</span></span>
3. <span data-ttu-id="61aea-125">I åtgärdsfönstret, välj **Hämta** och välj sedan **konfigurationsfil**.</span><span class="sxs-lookup"><span data-stu-id="61aea-125">On the Action Pane, select **Download**, and then select **Configuration file**.</span></span>
4. <span data-ttu-id="61aea-126">Välj **Hämta** och välj sedan **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="61aea-126">Select **Download**, and then select **Retail Modern POS**.</span></span> 
5. <span data-ttu-id="61aea-127">När hämtningen av filen **ModernPOSSetup.exe** är klar väljer du **Öppna fil**.</span><span class="sxs-lookup"><span data-stu-id="61aea-127">When download of the **ModernPOSSetup.exe** file is completed, select **Open file**.</span></span>

    ![Öppna fil](./dev-itpro/media/PAYMENTS/openfile.png)

6. <span data-ttu-id="61aea-129">Välj **Nästa** om du vill gå igenom installationsprocessen.</span><span class="sxs-lookup"><span data-stu-id="61aea-129">Select **Next** to go through the installation process.</span></span> <span data-ttu-id="61aea-130">När installationen är klar, välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="61aea-130">When installation is completed, select **Close**.</span></span>

### <a name="activate-modern-pos"></a><span data-ttu-id="61aea-131">Aktivera Modern POS</span><span class="sxs-lookup"><span data-stu-id="61aea-131">Activate Modern POS</span></span>

1. <span data-ttu-id="61aea-132">På Windows-skrivbordet, välj knappen **Start** och ange **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="61aea-132">On the Windows desktop, select the **Start** button, and enter **Retail Modern POS**.</span></span>
2. <span data-ttu-id="61aea-133">Välj den **Retail Modern POS**-app som ska initiera aktiveringen.</span><span class="sxs-lookup"><span data-stu-id="61aea-133">Select the **Retail Modern POS** application to initiate activation.</span></span>
3. <span data-ttu-id="61aea-134">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="61aea-134">Select **Next**.</span></span> <span data-ttu-id="61aea-135">Fälten **Server-URL**, **Enhets-ID** och **Kassanummer** ska vara förinställda genom att använda information från konfigurationsfilen som du hämtade i föregående procedur.</span><span class="sxs-lookup"><span data-stu-id="61aea-135">The **Server URL**, **Device ID**, and **Register number** fields should be preset by using information from the configuration file that you downloaded in the previous procedure.</span></span>
4. <span data-ttu-id="61aea-136">Välj **aktivera**.</span><span class="sxs-lookup"><span data-stu-id="61aea-136">Select **Activate**.</span></span>
5. <span data-ttu-id="61aea-137">En dialogrutan för verifiering visas.</span><span class="sxs-lookup"><span data-stu-id="61aea-137">An authentication dialog box appears.</span></span> <span data-ttu-id="61aea-138">Välj det konto som använder e-postadressen som tidigare kopplades till medarbetaren **000713 - Anders Collette**.</span><span class="sxs-lookup"><span data-stu-id="61aea-138">Select the account that uses the email address that was previously associated with worker **000713 - Andrew Collette**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="61aea-139">Om du ännu inte har associerat en medarbetare med din identitet kommer aktiveringen att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="61aea-139">If you haven't yet associated a worker with your identity, activation will be unsuccessful.</span></span> <span data-ttu-id="61aea-140">Följ i så fall instruktionerna under avsnittet "Associera arbetare med din identitet", i ämnet [Konfigurera en utvärderingsmiljö för Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).</span><span class="sxs-lookup"><span data-stu-id="61aea-140">In this case, follow the steps under the "Associate a worker with your identity" section in the [Configure a Dynamics 365 Commerce evaluation environment](cpe-post-provisioning.md#associate-a-worker-with-your-identity) topic.</span></span>
    
6. <span data-ttu-id="61aea-141">När du uppmanas att låta din organisation hantera enheten väljer du **Endast den här appen**.</span><span class="sxs-lookup"><span data-stu-id="61aea-141">When you're prompted to let your organization manage the device, select **This app only**.</span></span>
7. <span data-ttu-id="61aea-142">När aktiveringen är slutförd, välj **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="61aea-142">When activation is completed, select **Get started**.</span></span>

### <a name="enable-bopis-in-modern-pos"></a><span data-ttu-id="61aea-143">Aktivera BOPIS i Modern POS</span><span class="sxs-lookup"><span data-stu-id="61aea-143">Enable BOPIS in Modern POS</span></span>

1. <span data-ttu-id="61aea-144">Logga in på Modern POS genom att använda **000713** som operatörs-ID och **123** som lösenord.</span><span class="sxs-lookup"><span data-stu-id="61aea-144">Sign in to Modern POS by using **000713** as the operator ID and **123** as the password.</span></span>
2. <span data-ttu-id="61aea-145">Medan den inledande genomgångsvideon spelas upp markerar du de två kryssrutorna i det nedre vänstra hörnet av dialogrutan och stänger sedan dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="61aea-145">While the introductory walkthrough video is playing, select the two check boxes in the lower-left corner of the dialog box, and then close the dialog box.</span></span>
3. <span data-ttu-id="61aea-146">Om du inte uppmanas att stänga skiftet rullar du till höger på **Välkomstsidan**, väljer **Stäng skift** och loggar in igen i kassan.</span><span class="sxs-lookup"><span data-stu-id="61aea-146">If you aren't prompted to close the shift, scroll to the right on the **Welcome** page, select **Close shift**, and then sign back in to the POS.</span></span>
4. <span data-ttu-id="61aea-147">När du har loggat in väljer du **Utföra en åtgärd som inte är en lådåtgärd** när du uppmanas.</span><span class="sxs-lookup"><span data-stu-id="61aea-147">After you're signed in, when you're prompted, select **Perform a non-drawer operation**.</span></span>
5. <span data-ttu-id="61aea-148">På **Välkomstsidan** bläddra till höger och välj åtgärden **Välj maskinvarustation**.</span><span class="sxs-lookup"><span data-stu-id="61aea-148">On the **Welcome** page, scroll to the right, and select the **Select hardware station** operation.</span></span>
6. <span data-ttu-id="61aea-149">Välj **hantera**, ställ in alternativet **Använd maskinvarustation** till **På** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="61aea-149">Select **Manage**, set the **Use hardware station** option to **On**, and then select **OK**.</span></span>
7. <span data-ttu-id="61aea-150">Logga ut från kassan och logga sedan in igen.</span><span class="sxs-lookup"><span data-stu-id="61aea-150">Sign out of the POS, and then sign back in.</span></span>
8. <span data-ttu-id="61aea-151">När du har loggat in väljer du **Öppna ett nytt skift** och väljer sedan **Kassalåda**.</span><span class="sxs-lookup"><span data-stu-id="61aea-151">After you're signed in, select **Open a new shift**, and then select **Drawer**.</span></span>

## <a name="complete-a-bopis-scenario"></a><span data-ttu-id="61aea-152">Slutföra ett BOPIS-scenario</span><span class="sxs-lookup"><span data-stu-id="61aea-152">Complete a BOPIS scenario</span></span>

### <a name="create-a-storefront-order-for-in-store-pickup"></a><span data-ttu-id="61aea-153">Skapa en referensbutiken för upphämtning i butik</span><span class="sxs-lookup"><span data-stu-id="61aea-153">Create a storefront order for in-store pickup</span></span>

1. <span data-ttu-id="61aea-154">Gå till den URL som du angav i steget [Initiera e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) under konfigurationen av miljön.</span><span class="sxs-lookup"><span data-stu-id="61aea-154">Go to the URL that you specified in the [Initialize e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) step during environment configuration.</span></span>
2. <span data-ttu-id="61aea-155">Välj en artikel och välj **Lägg till i kundvagn**.</span><span class="sxs-lookup"><span data-stu-id="61aea-155">Select an item, and select **Add to cart**.</span></span>
3. <span data-ttu-id="61aea-156">På sidan för shoppingväska väljer du **Hämta den här** för den orderrad som du just har lagt till.</span><span class="sxs-lookup"><span data-stu-id="61aea-156">On the shopping bag page, select **Pick this up** for the order line that you just added.</span></span>
4. <span data-ttu-id="61aea-157">I dialogrutan **Välj en butik** anger du **San Francisco** och välj sedan knappen **Sök**.</span><span class="sxs-lookup"><span data-stu-id="61aea-157">In the **Select a store** dialog box, enter **San Francisco**, and then select the **Search** button.</span></span>
5. <span data-ttu-id="61aea-158">Leta reda på San Francisco-butiken i resultat listan och välj **Hämta den här**.</span><span class="sxs-lookup"><span data-stu-id="61aea-158">In the list of results, find the San Francisco store, and select **Pick up here**.</span></span>
6. <span data-ttu-id="61aea-159">På sidan för shoppingväska, välj **Gå till kassan som gäst**.</span><span class="sxs-lookup"><span data-stu-id="61aea-159">On the shopping bag page, select **Checkout as Guest**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="61aea-160">Om du vill fortsätta till kassan måste du acceptera cookie-meddelandet.</span><span class="sxs-lookup"><span data-stu-id="61aea-160">To continue with checkout, you must accept the cookie notice.</span></span> <span data-ttu-id="61aea-161">Det här meddelandet visas som en banderoll högst upp på kassasidan.</span><span class="sxs-lookup"><span data-stu-id="61aea-161">This notice appears as a banner at the top of the checkout page.</span></span>

7. <span data-ttu-id="61aea-162">Ange följande information för betalningsmetoden för kreditkort:</span><span class="sxs-lookup"><span data-stu-id="61aea-162">For the credit card payment method, enter the following details:</span></span>

    - <span data-ttu-id="61aea-163">**Kortinnehavarens namn**: Ange vilket namn som helst.</span><span class="sxs-lookup"><span data-stu-id="61aea-163">**Cardholder name:** Enter any name.</span></span>
    - <span data-ttu-id="61aea-164">**Kortnummer:** ange **4111-1111-1111-1111**.</span><span class="sxs-lookup"><span data-stu-id="61aea-164">**Card number:** Enter **4111-1111-1111-1111**.</span></span>
    - <span data-ttu-id="61aea-165">**Utgångsdatum:** Ange **10/20**.</span><span class="sxs-lookup"><span data-stu-id="61aea-165">**Expiration date:** Enter **10/20**.</span></span>
    - <span data-ttu-id="61aea-166">**Kortverifieringsnummer (CVV) kod:** Ange **737**.</span><span class="sxs-lookup"><span data-stu-id="61aea-166">**Card verification value (CVV) code:** Enter **737**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="61aea-167">Du bör aldrig försöka använda äkta kreditkortsinformation på testwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="61aea-167">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

8. <span data-ttu-id="61aea-168">Fortsätt i kassan genom att ange information om faktureringsadressen och välj sedan **Spara och fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="61aea-168">Continue with checkout by entering details of the billing address, and then select **Save and continue**.</span></span>
9. <span data-ttu-id="61aea-169">När beställningen är klar att göras, välj **Kassa**.</span><span class="sxs-lookup"><span data-stu-id="61aea-169">When the order is ready to be placed, select **Checkout**.</span></span>

### <a name="synchronize-online-orders-to-the-back-office"></a><span data-ttu-id="61aea-170">Synkronisera onlinebeställningar till backoffice</span><span class="sxs-lookup"><span data-stu-id="61aea-170">Synchronize online orders to the back office</span></span>

<span data-ttu-id="61aea-171">Information om hur du synkroniserar onlinebeställningar finns i [bokföra online försäljning och betalningar](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span><span class="sxs-lookup"><span data-stu-id="61aea-171">For information about how to synchronize online orders, see [Posting of online sales and payments](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span></span>

### <a name="pick-up-an-order-in-the-store"></a><span data-ttu-id="61aea-172">Hämta en beställning i butik</span><span class="sxs-lookup"><span data-stu-id="61aea-172">Pick up an order in the store</span></span>

1. <span data-ttu-id="61aea-173">Logga in i kassan.</span><span class="sxs-lookup"><span data-stu-id="61aea-173">Sign in to the POS.</span></span>
2. <span data-ttu-id="61aea-174">På **Välkomstskärmen**, välj **Orderuppfyllelse**</span><span class="sxs-lookup"><span data-stu-id="61aea-174">On the **Welcome** screen, select **Order fulfillment**</span></span>
3. <span data-ttu-id="61aea-175">I listan över artiklar för upphämtning markerar du raden från den beställning som gjorts online.</span><span class="sxs-lookup"><span data-stu-id="61aea-175">In the list of items for pickup, select the line from the order that was placed online.</span></span>
4. <span data-ttu-id="61aea-176">När beställningsraden är vald, välj **Hämta**.</span><span class="sxs-lookup"><span data-stu-id="61aea-176">While the order line is selected, select **Pick up**.</span></span>

    <span data-ttu-id="61aea-177">Radartikeln läggs till transaktionsskärmen och **$0,00** visas som saldo som förfaller.</span><span class="sxs-lookup"><span data-stu-id="61aea-177">The line item is added to the transaction screen, and **$0.00** is shown as the balance that is due.</span></span>

5. <span data-ttu-id="61aea-178">Välj saldo som förfaller för **$0,00** eller välj valfri betalningsmetod för att avsluta transaktionen.</span><span class="sxs-lookup"><span data-stu-id="61aea-178">Select the balance due of **$0.00**, or select any payment method to conclude the transaction.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="61aea-179">Felsökning</span><span class="sxs-lookup"><span data-stu-id="61aea-179">Troubleshooting</span></span>

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a><span data-ttu-id="61aea-180">Onlinebeställningar som hämtas i kassan har en skuld som inte är noll</span><span class="sxs-lookup"><span data-stu-id="61aea-180">Online orders that are retrieved in the POS have a non-zero balance due</span></span>

<span data-ttu-id="61aea-181">När en beställning ska hämtas i butik, om förfallet saldo inte är 0 (noll), kontrollerar du att Modern POS används och att maskinvarustationen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="61aea-181">When an order is retrieved for in-store pickup, if the balance due isn't 0 (zero), make sure that Modern POS is being used, and that the hardware station is active.</span></span> <span data-ttu-id="61aea-182">Om Cloud POS eller Modern POS för iOS används ska du kontrollera att en delad maskinvarustation är aktiv.</span><span class="sxs-lookup"><span data-stu-id="61aea-182">If Cloud POS or Modern POS for iOS is being used, make sure that a shared hardware station is active.</span></span> <span data-ttu-id="61aea-183">Någon form av aktiv maskinvarustation krävs för att hämta betalningar som har gjorts online.</span><span class="sxs-lookup"><span data-stu-id="61aea-183">Some form of active hardware station is required to retrieve payments that were made online.</span></span>

### <a name="general-issues-with-payment-capture"></a><span data-ttu-id="61aea-184">Allmänna utleveranser vid betalningsregistrering</span><span class="sxs-lookup"><span data-stu-id="61aea-184">General issues with payment capture</span></span>

<span data-ttu-id="61aea-185">För alla allmänna problem bör du alltid läsa händelseloggarna i Modern POS-eller Internet Information Services (IIS) maskinvarustation som ett första steg.</span><span class="sxs-lookup"><span data-stu-id="61aea-185">For all general issues, you should always consult the Modern POS or Internet Information Services (IIS) Hardware Station event logs as a first step.</span></span> <span data-ttu-id="61aea-186">Dessa loggar finns under följande noder i Windows-händelselogg:</span><span class="sxs-lookup"><span data-stu-id="61aea-186">You can find these logs under the following nodes in the Windows event log:</span></span>

- <span data-ttu-id="61aea-187">Program- och tjänstloggar \> Microsoft \> Dynamics \> Commerce-ModernPOS</span><span class="sxs-lookup"><span data-stu-id="61aea-187">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-ModernPOS</span></span>
- <span data-ttu-id="61aea-188">Program- och tjänstloggar \> Microsoft \> Dynamics \> Commerce-Maskinvarustation</span><span class="sxs-lookup"><span data-stu-id="61aea-188">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-Hardware Station</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61aea-189">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="61aea-189">Additional resources</span></span>

[<span data-ttu-id="61aea-190">Dynamics 365 Commerce utvärderingsmiljö – översikt</span><span class="sxs-lookup"><span data-stu-id="61aea-190">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="61aea-191">Etablera en Dynamics 365 Commerce utvärderingsmiljön</span><span class="sxs-lookup"><span data-stu-id="61aea-191">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="61aea-192">Konfigurera valfria funktioner för en Dynamics 365 Commerce utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="61aea-192">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="61aea-193">Dynamics 365 Commerce utvärderingsmiljö – vanliga frågor</span><span class="sxs-lookup"><span data-stu-id="61aea-193">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="61aea-194">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="61aea-194">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="61aea-195">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="61aea-195">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="61aea-196">Microsoft Azure-portal</span><span class="sxs-lookup"><span data-stu-id="61aea-196">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="61aea-197">Dynamics 365 Commerce webbplatsen</span><span class="sxs-lookup"><span data-stu-id="61aea-197">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="61aea-198">Adyen-betalningskoppling</span><span class="sxs-lookup"><span data-stu-id="61aea-198">Adyen payment connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)

[<span data-ttu-id="61aea-199">Spara betalningsinstrument online med Adyen-kopplingen</span><span class="sxs-lookup"><span data-stu-id="61aea-199">Saving online payment instruments with the Adyen connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector-listpi)

[<span data-ttu-id="61aea-200">Översikt över betalningar i flera kanaler</span><span class="sxs-lookup"><span data-stu-id="61aea-200">Omni-channel payments overview</span></span>](https://docs.microsoft.com/dynamics365/commerce/omni-channel-payments)
