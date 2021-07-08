---
title: Vad är nytt eller ändrat i mobilappen Warehouse Management
description: Det här ämnet visar en lista med nya och ändrade funktioner för varje frisläppt version av mobilappen Warehouse Management för Microsoft Dynamics 365 Supply Chain Management.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261800"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="14193-103">Vad är nytt eller ändrat i mobilappen Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="14193-103">What's new or changed in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="14193-104">Detta ämne listar nya funktioner, korrigeringar, förbättringar och kända problem för varje släppt version av mobilappen Warehouse Management för Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="14193-104">This topic lists new features, fixes, improvements, and known issues for each released version of the Warehouse Management mobile app for Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="version-2060"></a><span data-ttu-id="14193-105">Version 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="14193-105">Version 2.0.6.0</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2060"></a><span data-ttu-id="14193-106">Nya funktioner, korrigeringar och förbättringar i version 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="14193-106">New features, fixes, and improvements in version 2.0.6.0</span></span>

<span data-ttu-id="14193-107">I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:</span><span class="sxs-lookup"><span data-stu-id="14193-107">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="14193-108">I demoläget visas nu alla etiketter på enhetens språk.</span><span class="sxs-lookup"><span data-stu-id="14193-108">Demo mode now shows all labels in the device language.</span></span>
- <span data-ttu-id="14193-109">Det är mindre sannolikt att du får följande felmeddelande: "Det går inte att hitta någon lämplig vy för den angivna storleken."</span><span class="sxs-lookup"><span data-stu-id="14193-109">You're less likely to receive the following error message: "Cannot find a suitable view for the specified size."</span></span>
- <span data-ttu-id="14193-110">Minimihöjden för arbetskort har ökat (i fall där tre eller färre fält har konfigurerats för att visas i arbetslistan).</span><span class="sxs-lookup"><span data-stu-id="14193-110">The minimum height for work cards has been increased (for cases where three or fewer fields are configured to appear in the work list).</span></span>
- <span data-ttu-id="14193-111">Marginalerna (tona ut) har förbättrats längst ner på detaljkorten.</span><span class="sxs-lookup"><span data-stu-id="14193-111">Margins (fade out) at the bottom of details cards have been improved.</span></span>
- <span data-ttu-id="14193-112">Ogiltiga symboler i XML-filer som utbyts med servern hanteras nu.</span><span class="sxs-lookup"><span data-stu-id="14193-112">Invalid symbols in XML files that are exchanged with the server are now handled gracefully.</span></span> <span data-ttu-id="14193-113">(Tecken som inte kan skrivas ut hanteras nu för respit så att programmet inte längre slutar svara.)</span><span class="sxs-lookup"><span data-stu-id="14193-113">(For example, non-printable characters are now handled gracefully and no longer cause the app to stop responding.)</span></span>
- <span data-ttu-id="14193-114">HTTP-fel (som "fel 503") när en serverbegäran skickas hanteras nu utan fel.</span><span class="sxs-lookup"><span data-stu-id="14193-114">HTTP errors (such as "error 503") when a server request is submitted are now handled gracefully.</span></span>
- <span data-ttu-id="14193-115">Medan ett fel visas visas inte längre alternativlistan automatiskt för kombinationsrutakontroller.</span><span class="sxs-lookup"><span data-stu-id="14193-115">While an error is being shown, the options list is no longer automatically shown for combo box controls.</span></span>
- <span data-ttu-id="14193-116">Programmet slutar inte längre svara på grund av den visningsorientering som har valts i användarinställningarna.</span><span class="sxs-lookup"><span data-stu-id="14193-116">The app no longer stops responding because of the display orientation that is selected in user settings.</span></span>
- <span data-ttu-id="14193-117">Produktbilder visas nu i självbetjäningsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="14193-117">Product images are now shown in self-service environments.</span></span> <span data-ttu-id="14193-118">(Den här ändringen gäller endast för lågupplösningsversioner.</span><span class="sxs-lookup"><span data-stu-id="14193-118">(This change applies to low-resolution versions only.</span></span> <span data-ttu-id="14193-119">Filhanteringstjänsten har inte stöd för bilder av full storlek i självbetjäningmiljöer.)</span><span class="sxs-lookup"><span data-stu-id="14193-119">The file management service doesn't support full-sized images in self-service environments.)</span></span>
- <span data-ttu-id="14193-120">Ett problem som involverar korta plockningar med nollkvantitet har lösts.</span><span class="sxs-lookup"><span data-stu-id="14193-120">An issue that involved zero-quantity short picks has been fixed.</span></span>
- <span data-ttu-id="14193-121">Programmet slutar inte längre att svara när ett detaljkort visar flera identiska fält.</span><span class="sxs-lookup"><span data-stu-id="14193-121">The app no longer stops responding when a details card shows multiple identical fields.</span></span>

### <a name="known-issues-in-version-2060"></a><span data-ttu-id="14193-122">Kända problem i version 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="14193-122">Known issues in version 2.0.6.0</span></span>

<span data-ttu-id="14193-123">Följande kända problem finns i den här versionen:</span><span class="sxs-lookup"><span data-stu-id="14193-123">The following known issues exist in this version:</span></span>

- <span data-ttu-id="14193-124">Appen (särskilt arbetslistan) blir slut med tiden.</span><span class="sxs-lookup"><span data-stu-id="14193-124">The app (especially the work list) becomes slower over time.</span></span>
- <span data-ttu-id="14193-125">**Windows-version:** När USB används för skanning i Windows, orsakar inkonsekventa resultat att skannade symboler blandas ihop.</span><span class="sxs-lookup"><span data-stu-id="14193-125">**Windows version:** When a USB gun is used for scanning on Windows, inconsistent results cause scanned symbols to be mixed up.</span></span>

## <a name="version-2050"></a><span data-ttu-id="14193-126">Version 2.0.5.0</span><span class="sxs-lookup"><span data-stu-id="14193-126">Version 2.0.5.0</span></span>

<span data-ttu-id="14193-127">I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:</span><span class="sxs-lookup"><span data-stu-id="14193-127">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="14193-128">Klienthemligheten är inte längre dold i anslutningsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="14193-128">The client secret is no longer hidden in the connection settings setup.</span></span>
- <span data-ttu-id="14193-129">Du kan nu länge trycka på en text för att se den helt.</span><span class="sxs-lookup"><span data-stu-id="14193-129">You can now long-press on any text to see it fully.</span></span>
- <span data-ttu-id="14193-130">Felmeddelandet när lagringsbehörigheter saknas har förbättrats.</span><span class="sxs-lookup"><span data-stu-id="14193-130">The error message when storage permissions are missing has been improved.</span></span>
- <span data-ttu-id="14193-131">Nya kontrollsekvenser har lagts till för vissa flöden.</span><span class="sxs-lookup"><span data-stu-id="14193-131">New control sequences have been added for some flows.</span></span>
- <span data-ttu-id="14193-132">Knappen Skicka blir inte längre fel tillgänglig på grund av fönsterstorleken.</span><span class="sxs-lookup"><span data-stu-id="14193-132">The submit button no longer incorrectly becomes available because of the window size.</span></span>
- <span data-ttu-id="14193-133">Skjutreglagen kan nu fortsätta på mindre skärmar när större knappstorlekar används.</span><span class="sxs-lookup"><span data-stu-id="14193-133">Sliders can now proceed on smaller screens when larger button sizes are used.</span></span>
- <span data-ttu-id="14193-134">Den fyra knappen är inte längre avklippt.</span><span class="sxs-lookup"><span data-stu-id="14193-134">The four-button overlay is no longer cut off.</span></span>
- <span data-ttu-id="14193-135">Tangentbordet har nu stöd för knappen Radera.</span><span class="sxs-lookup"><span data-stu-id="14193-135">The keyboard now supports the delete button.</span></span>
- <span data-ttu-id="14193-136">Ett problem med ett problem som kan uppstå när du använder tangentbordet har lösts in.</span><span class="sxs-lookup"><span data-stu-id="14193-136">A brightness issue that could occur when the keyboard is pressed has been fixed.</span></span>
- <span data-ttu-id="14193-137">Olika problem med demodata har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="14193-137">Various demo data issues have been fixed.</span></span>
- <span data-ttu-id="14193-138">Ett problem som påverkas av numeriska fält på detaljsidan har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="14193-138">An issue that affected numeric fields on the details page has been fixed.</span></span>
- <span data-ttu-id="14193-139">Ibland försvinner inte längre skärmtangentbordet på vissa enheter.</span><span class="sxs-lookup"><span data-stu-id="14193-139">The screen keyboard no longer occasionally disappears on some devices.</span></span>
- <span data-ttu-id="14193-140">Olika användargränssnitt (UI) har åtgärdats, till exempel så att det påverkade bakgrundsfärgen och positionering.</span><span class="sxs-lookup"><span data-stu-id="14193-140">Various user interface (UI) bugs have been fixed, such as bugs that affected the background color and positioning.</span></span>
- <span data-ttu-id="14193-141">Användargränssnittet för ryska har förbättrats.</span><span class="sxs-lookup"><span data-stu-id="14193-141">The Russian-language UI has been improved.</span></span>
- <span data-ttu-id="14193-142">Olika problem som gör att systemet inte svarar har lösts.</span><span class="sxs-lookup"><span data-stu-id="14193-142">Various issues that caused the system to stop responding have been fixed.</span></span>
- <span data-ttu-id="14193-143">Ett problem som gick att öppna kalkylatorn på nytt har lösts.</span><span class="sxs-lookup"><span data-stu-id="14193-143">An issue that was related to reopening the calculator has been fixed.</span></span>
- <span data-ttu-id="14193-144">**Android version:** Ett problem som orsakade Android 4.4 att sluta svara vid start har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="14193-144">**Android version:** An issue that caused Android 4.4 to stop responding on startup has been fixed.</span></span>
- <span data-ttu-id="14193-145">**Android version:** minimiskalning har reducerats till 50 procent.</span><span class="sxs-lookup"><span data-stu-id="14193-145">**Android version:** Minimum scaling has been reduced to 50 percent.</span></span>

## <a name="version-2040"></a><span data-ttu-id="14193-146">Version 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="14193-146">Version 2.0.4.0</span></span>

<span data-ttu-id="14193-147">Version 2.0.4.0 var den första allmänt tillgängliga versionen av mobilappen Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="14193-147">Version 2.0.4.0 was the first generally available release of the Warehouse Management mobile app.</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2040"></a><span data-ttu-id="14193-148">Nya funktioner, korrigeringar och förbättringar i version 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="14193-148">New features, fixes, and improvements in version 2.0.4.0</span></span>

<span data-ttu-id="14193-149">Denna version introducerar följande nya funktioner, korrigeringar och förbättringar som inte är tillgängliga i förhandsgranskningsversionen:</span><span class="sxs-lookup"><span data-stu-id="14193-149">This version introduces the following new features, fixes, and improvements that weren't available in the preview version:</span></span>

- <span data-ttu-id="14193-150">Om ett detaljkort innehåller två etiketter med identiska data är en av etiketterna dold.</span><span class="sxs-lookup"><span data-stu-id="14193-150">If a details card includes two labels that have identical data, one of the labels is hidden.</span></span>
- <span data-ttu-id="14193-151">Specialtecken visas nu som standard och alternativet för att dölja dem tas bort från användarinställningarna.</span><span class="sxs-lookup"><span data-stu-id="14193-151">Special characters are now shown by default, and the option to hide them has been removed from user settings.</span></span>
- <span data-ttu-id="14193-152">Inaktiverade skicka-knappar visas nu som inte tillgängliga im-visning.</span><span class="sxs-lookup"><span data-stu-id="14193-152">Disabled submit buttons are now shown as unavailable in compact arm-held view.</span></span>
- <span data-ttu-id="14193-153">En ändring av ordningslogiken för kontroller ser till att skalningen blir smidigare mellan enheter.</span><span class="sxs-lookup"><span data-stu-id="14193-153">A change to the sequencing logic for controls ensures smoother scaling across devices.</span></span> <span data-ttu-id="14193-154">Det är därför mindre nödvändigt att justera skalningen av teckensnitt eller knappar.</span><span class="sxs-lookup"><span data-stu-id="14193-154">Therefore, there is less need to adjust the scaling of fonts or buttons.</span></span>
- <span data-ttu-id="14193-155">Standardfärgtemat har ändrats till *Mörk*.</span><span class="sxs-lookup"><span data-stu-id="14193-155">The default color theme has been changed to *Dark*.</span></span>
- <span data-ttu-id="14193-156">Ikonen som saknas för den inaktiverade skicka-knappen har lagts till i tittat.</span><span class="sxs-lookup"><span data-stu-id="14193-156">The missing icon for the disabled submit button has been added in ribbon view.</span></span>
- <span data-ttu-id="14193-157">Time-out-undantag tar dig nu till anslutningssidan istället för att visa ett radfel.</span><span class="sxs-lookup"><span data-stu-id="14193-157">Time-out exceptions now take you to the connection page instead of showing an in-line error.</span></span>
- <span data-ttu-id="14193-158">Om det inte finns någon åtgärd att skicka (till exempel **OK**, **Ja**, **Acceptera**, **Klar** eller **Avslutad**), inaktiveras knappen Skicka.</span><span class="sxs-lookup"><span data-stu-id="14193-158">If no submit action is available (such as **OK**, **Yes**, **Accept**, **Done**, or **Finished**), the submit button will be disabled.</span></span>
- <span data-ttu-id="14193-159">Appens stabilitet har förbättrats.</span><span class="sxs-lookup"><span data-stu-id="14193-159">App stability has been improved.</span></span>
- <span data-ttu-id="14193-160">Det finns en korrigering för säkerhetsrisk [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span><span class="sxs-lookup"><span data-stu-id="14193-160">There is a fix for security vulnerability [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span></span>
- <span data-ttu-id="14193-161">**Windows-version:** Ett problem i Windows, där menyerna inte var svarande efter det att fönstret ändrades, har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="14193-161">**Windows version:** An issue on Windows, where menus were unresponsive after the window was resized, has been fixed.</span></span>

### <a name="known-issue-in-version-2040"></a><span data-ttu-id="14193-162">Kända problem i version 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="14193-162">Known issue in version 2.0.4.0</span></span>

<span data-ttu-id="14193-163">Följande kända problem finns i den här versionen:</span><span class="sxs-lookup"><span data-stu-id="14193-163">The following known issue exists in this version:</span></span>

- <span data-ttu-id="14193-164">Den här versionen har problem med enheter som använder Android 4.4.</span><span class="sxs-lookup"><span data-stu-id="14193-164">This version has an issue with devices that use Android 4.4.</span></span> <span data-ttu-id="14193-165">Du kan få problem när du använder programmet i den här Android versionen.</span><span class="sxs-lookup"><span data-stu-id="14193-165">You might experience issues when you use the app on this Android version.</span></span>
