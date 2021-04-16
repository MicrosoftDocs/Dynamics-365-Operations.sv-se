---
title: NF-e anpassad certifikatvalidering
description: Det här avsnittet innehåller information om hur du aktiverar och använder det anpassade NF-e-certifikatet.
author: gionoder
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 895513f51798a797ebf59f8a5be4f5cde006726d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813978"
---
# <a name="nf-e-custom-certificate-validation"></a><span data-ttu-id="d0b6f-103">NF-e anpassad certifikatvalidering</span><span class="sxs-lookup"><span data-stu-id="d0b6f-103">NF-e custom certificate validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0b6f-104">När du aktiverar funktionen för verifiering av anpassat NF-e-certifikat kan du använda anpassade valideringar för att ansluta till webbtjänsterna.</span><span class="sxs-lookup"><span data-stu-id="d0b6f-104">When you turn the NF-e custom certificate verification feature, custom validation allows a connection with the web services.</span></span> <span data-ttu-id="d0b6f-105">Den här anslutningen krävs för att överföra NF-e och få behörighet från SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="d0b6f-105">This connection is required to transmit NF-e and receive authorization from SEFAZ.</span></span>

<span data-ttu-id="d0b6f-106">Egenskapen **Serverns syfte att autentiseras** från certifikat V5 utfärdas av den brasilianska rotcertifikatsmyndigheten.</span><span class="sxs-lookup"><span data-stu-id="d0b6f-106">The **Server authentication purpose** property from the certificate V5 is issued by the Brazilian Root Certificate Authority.</span></span> <span data-ttu-id="d0b6f-107">Den här egenskapen är som standard inaktiverad och måste aktiveras manuellt.</span><span class="sxs-lookup"><span data-stu-id="d0b6f-107">This property is turned off by default and must be manually enabled.</span></span> <span data-ttu-id="d0b6f-108">I vissa fall kan den automatiska certifikatuppdateringen växla egenskapen till att inte längre aktiveras.</span><span class="sxs-lookup"><span data-stu-id="d0b6f-108">In some circumstances, the automatic certificate update can switch this property to no longer be enabled.</span></span> <span data-ttu-id="d0b6f-109">Om detta inträffar, påverkas TLS-anslutningen och den är inte längre betrodd.</span><span class="sxs-lookup"><span data-stu-id="d0b6f-109">If this happens, the TLS connection is affected and is no longer trusted.</span></span> <span data-ttu-id="d0b6f-110">Möjligheten att utfärda NF-e i produktionsmiljöer för stater i Minas Gerais (MG) och Paraná (PR) påverkas också.</span><span class="sxs-lookup"><span data-stu-id="d0b6f-110">The ability to issue NF-e on production environments for states of Minas Gerais (MG) and Paraná (PR) states is also impacted.</span></span>

<span data-ttu-id="d0b6f-111">Den här uppdateringen möjliggör en alternativ lösning för certifikat validering, vilket innebär att det är möjligt att upprätta en säker kommunikation.</span><span class="sxs-lookup"><span data-stu-id="d0b6f-111">This update allows for an alternative solution for certificate validation, which means that it’s possible to establish a secure communication.</span></span>




[!INCLUDE[footer-include](../../includes/footer-banner.md)]