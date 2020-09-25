---
title: Kolekcje schematów OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 90899a123b3dafcd47a50ef8f6eb003938b22a03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186942"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="2246d-102">Kolekcje schematów OLE DB</span><span class="sxs-lookup"><span data-stu-id="2246d-102">OLE DB Schema Collections</span></span>

<span data-ttu-id="2246d-103">W tej sekcji omówiono obsługę kolekcji schematów dla OLE DB dostawców dla Microsoft SQL Server, Oracle i Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="2246d-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="2246d-104">Dostawca OLE DB Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="2246d-104">Microsoft SQL Server OLE DB Provider</span></span>  

 <span data-ttu-id="2246d-105">Sterownik OLE DB Microsoft SQL Server obsługuje następujące kolekcje schematów oprócz wspólnych kolekcji schematów:</span><span class="sxs-lookup"><span data-stu-id="2246d-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="2246d-106">Tabele</span><span class="sxs-lookup"><span data-stu-id="2246d-106">Tables</span></span>  
  
- <span data-ttu-id="2246d-107">Kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-107">Columns</span></span>  
  
- <span data-ttu-id="2246d-108">Procedury</span><span class="sxs-lookup"><span data-stu-id="2246d-108">Procedures</span></span>  
  
- <span data-ttu-id="2246d-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2246d-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="2246d-110">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2246d-110">Catalog</span></span>  
  
- <span data-ttu-id="2246d-111">Indeksy</span><span class="sxs-lookup"><span data-stu-id="2246d-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2246d-112">Tabele</span><span class="sxs-lookup"><span data-stu-id="2246d-112">Tables</span></span>  
  
|<span data-ttu-id="2246d-113">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-113">ColumnName</span></span>|<span data-ttu-id="2246d-114">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-115">TABLE_CATALOG</span></span>|<span data-ttu-id="2246d-116">String</span><span class="sxs-lookup"><span data-stu-id="2246d-116">String</span></span>|  
|<span data-ttu-id="2246d-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="2246d-118">String</span><span class="sxs-lookup"><span data-stu-id="2246d-118">String</span></span>|  
|<span data-ttu-id="2246d-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-119">TABLE_NAME</span></span>|<span data-ttu-id="2246d-120">String</span><span class="sxs-lookup"><span data-stu-id="2246d-120">String</span></span>|  
|<span data-ttu-id="2246d-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-121">TABLE_TYPE</span></span>|<span data-ttu-id="2246d-122">String</span><span class="sxs-lookup"><span data-stu-id="2246d-122">String</span></span>|  
|<span data-ttu-id="2246d-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-123">TABLE_GUID</span></span>|<span data-ttu-id="2246d-124">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-124">Guid</span></span>|  
|<span data-ttu-id="2246d-125">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-125">DESCRIPTION</span></span>|<span data-ttu-id="2246d-126">String</span><span class="sxs-lookup"><span data-stu-id="2246d-126">String</span></span>|  
|<span data-ttu-id="2246d-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2246d-127">TABLE_PROPID</span></span>|<span data-ttu-id="2246d-128">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-128">Int64</span></span>|  
|<span data-ttu-id="2246d-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2246d-129">DATE_CREATED</span></span>|<span data-ttu-id="2246d-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-130">DateTime</span></span>|  
|<span data-ttu-id="2246d-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2246d-131">DATE_MODIFIED</span></span>|<span data-ttu-id="2246d-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2246d-133">Kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-133">Columns</span></span>  
  
|<span data-ttu-id="2246d-134">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-134">ColumnName</span></span>|<span data-ttu-id="2246d-135">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-136">TABLE_CATALOG</span></span>|<span data-ttu-id="2246d-137">String</span><span class="sxs-lookup"><span data-stu-id="2246d-137">String</span></span>|  
|<span data-ttu-id="2246d-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="2246d-139">String</span><span class="sxs-lookup"><span data-stu-id="2246d-139">String</span></span>|  
|<span data-ttu-id="2246d-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-140">TABLE_NAME</span></span>|<span data-ttu-id="2246d-141">String</span><span class="sxs-lookup"><span data-stu-id="2246d-141">String</span></span>|  
|<span data-ttu-id="2246d-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-142">COLUMN_NAME</span></span>|<span data-ttu-id="2246d-143">String</span><span class="sxs-lookup"><span data-stu-id="2246d-143">String</span></span>|  
|<span data-ttu-id="2246d-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-144">COLUMN_GUID</span></span>|<span data-ttu-id="2246d-145">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-145">Guid</span></span>|  
|<span data-ttu-id="2246d-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2246d-146">COLUMN_PROPID</span></span>|<span data-ttu-id="2246d-147">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-147">Int64</span></span>|  
|<span data-ttu-id="2246d-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2246d-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="2246d-149">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-149">Int64</span></span>|  
|<span data-ttu-id="2246d-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2246d-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2246d-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-151">Boolean</span></span>|  
|<span data-ttu-id="2246d-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2246d-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2246d-153">String</span><span class="sxs-lookup"><span data-stu-id="2246d-153">String</span></span>|  
|<span data-ttu-id="2246d-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2246d-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="2246d-155">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-155">Int64</span></span>|  
|<span data-ttu-id="2246d-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2246d-156">IS_NULLABLE</span></span>|<span data-ttu-id="2246d-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-157">Boolean</span></span>|  
|<span data-ttu-id="2246d-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-158">DATA_TYPE</span></span>|<span data-ttu-id="2246d-159">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-159">Int32</span></span>|  
|<span data-ttu-id="2246d-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-160">TYPE_GUID</span></span>|<span data-ttu-id="2246d-161">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-161">Guid</span></span>|  
|<span data-ttu-id="2246d-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2246d-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2246d-163">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-163">Int64</span></span>|  
|<span data-ttu-id="2246d-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2246d-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2246d-165">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-165">Int64</span></span>|  
|<span data-ttu-id="2246d-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2246d-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2246d-167">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-167">Int32</span></span>|  
|<span data-ttu-id="2246d-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2246d-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="2246d-169">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-169">Int16</span></span>|  
|<span data-ttu-id="2246d-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2246d-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="2246d-171">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-171">Int64</span></span>|  
|<span data-ttu-id="2246d-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2246d-173">String</span><span class="sxs-lookup"><span data-stu-id="2246d-173">String</span></span>|  
|<span data-ttu-id="2246d-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2246d-175">String</span><span class="sxs-lookup"><span data-stu-id="2246d-175">String</span></span>|  
|<span data-ttu-id="2246d-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2246d-177">String</span><span class="sxs-lookup"><span data-stu-id="2246d-177">String</span></span>|  
|<span data-ttu-id="2246d-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="2246d-179">String</span><span class="sxs-lookup"><span data-stu-id="2246d-179">String</span></span>|  
|<span data-ttu-id="2246d-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2246d-181">String</span><span class="sxs-lookup"><span data-stu-id="2246d-181">String</span></span>|  
|<span data-ttu-id="2246d-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-182">COLLATION_NAME</span></span>|<span data-ttu-id="2246d-183">String</span><span class="sxs-lookup"><span data-stu-id="2246d-183">String</span></span>|  
|<span data-ttu-id="2246d-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2246d-185">String</span><span class="sxs-lookup"><span data-stu-id="2246d-185">String</span></span>|  
|<span data-ttu-id="2246d-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2246d-187">String</span><span class="sxs-lookup"><span data-stu-id="2246d-187">String</span></span>|  
|<span data-ttu-id="2246d-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-188">DOMAIN_NAME</span></span>|<span data-ttu-id="2246d-189">String</span><span class="sxs-lookup"><span data-stu-id="2246d-189">String</span></span>|  
|<span data-ttu-id="2246d-190">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-190">DESCRIPTION</span></span>|<span data-ttu-id="2246d-191">String</span><span class="sxs-lookup"><span data-stu-id="2246d-191">String</span></span>|  
|<span data-ttu-id="2246d-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="2246d-192">COLUMN_LCID</span></span>|<span data-ttu-id="2246d-193">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-193">Int32</span></span>|  
|<span data-ttu-id="2246d-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="2246d-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="2246d-195">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-195">Int32</span></span>|  
|<span data-ttu-id="2246d-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="2246d-196">COLUMN_SORTID</span></span>|<span data-ttu-id="2246d-197">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-197">Int32</span></span>|  
|<span data-ttu-id="2246d-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="2246d-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="2246d-199">Byte []</span><span class="sxs-lookup"><span data-stu-id="2246d-199">Byte[]</span></span>|  
|<span data-ttu-id="2246d-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="2246d-200">IS_COMPUTED</span></span>|<span data-ttu-id="2246d-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2246d-202">Procedury</span><span class="sxs-lookup"><span data-stu-id="2246d-202">Procedures</span></span>  
  
|<span data-ttu-id="2246d-203">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-203">ColumnName</span></span>|<span data-ttu-id="2246d-204">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2246d-206">String</span><span class="sxs-lookup"><span data-stu-id="2246d-206">String</span></span>|  
|<span data-ttu-id="2246d-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2246d-208">String</span><span class="sxs-lookup"><span data-stu-id="2246d-208">String</span></span>|  
|<span data-ttu-id="2246d-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="2246d-210">String</span><span class="sxs-lookup"><span data-stu-id="2246d-210">String</span></span>|  
|<span data-ttu-id="2246d-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2246d-212">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-212">Int16</span></span>|  
|<span data-ttu-id="2246d-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2246d-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2246d-214">String</span><span class="sxs-lookup"><span data-stu-id="2246d-214">String</span></span>|  
|<span data-ttu-id="2246d-215">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-215">DESCRIPTION</span></span>|<span data-ttu-id="2246d-216">String</span><span class="sxs-lookup"><span data-stu-id="2246d-216">String</span></span>|  
|<span data-ttu-id="2246d-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2246d-217">DATE_CREATED</span></span>|<span data-ttu-id="2246d-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-218">DateTime</span></span>|  
|<span data-ttu-id="2246d-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2246d-219">DATE_MODIFIED</span></span>|<span data-ttu-id="2246d-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="2246d-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2246d-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="2246d-222">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-222">ColumnName</span></span>|<span data-ttu-id="2246d-223">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2246d-225">String</span><span class="sxs-lookup"><span data-stu-id="2246d-225">String</span></span>|  
|<span data-ttu-id="2246d-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2246d-227">String</span><span class="sxs-lookup"><span data-stu-id="2246d-227">String</span></span>|  
|<span data-ttu-id="2246d-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="2246d-229">String</span><span class="sxs-lookup"><span data-stu-id="2246d-229">String</span></span>|  
|<span data-ttu-id="2246d-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-230">PARAMETER_NAME</span></span>|<span data-ttu-id="2246d-231">String</span><span class="sxs-lookup"><span data-stu-id="2246d-231">String</span></span>|  
|<span data-ttu-id="2246d-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2246d-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="2246d-233">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-233">Int32</span></span>|  
|<span data-ttu-id="2246d-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="2246d-235">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-235">Int32</span></span>|  
|<span data-ttu-id="2246d-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2246d-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="2246d-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-237">Boolean</span></span>|  
|<span data-ttu-id="2246d-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2246d-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="2246d-239">String</span><span class="sxs-lookup"><span data-stu-id="2246d-239">String</span></span>|  
|<span data-ttu-id="2246d-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2246d-240">IS_NULLABLE</span></span>|<span data-ttu-id="2246d-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-241">Boolean</span></span>|  
|<span data-ttu-id="2246d-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-242">DATA_TYPE</span></span>|<span data-ttu-id="2246d-243">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-243">Int32</span></span>|  
|<span data-ttu-id="2246d-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2246d-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2246d-245">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-245">Int64</span></span>|  
|<span data-ttu-id="2246d-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2246d-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2246d-247">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-247">Int64</span></span>|  
|<span data-ttu-id="2246d-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2246d-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2246d-249">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-249">Int32</span></span>|  
|<span data-ttu-id="2246d-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2246d-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="2246d-251">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-251">Int16</span></span>|  
|<span data-ttu-id="2246d-252">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-252">DESCRIPTION</span></span>|<span data-ttu-id="2246d-253">String</span><span class="sxs-lookup"><span data-stu-id="2246d-253">String</span></span>|  
|<span data-ttu-id="2246d-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-254">TYPE_NAME</span></span>|<span data-ttu-id="2246d-255">String</span><span class="sxs-lookup"><span data-stu-id="2246d-255">String</span></span>|  
|<span data-ttu-id="2246d-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="2246d-257">String</span><span class="sxs-lookup"><span data-stu-id="2246d-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="2246d-258">Wykaz</span><span class="sxs-lookup"><span data-stu-id="2246d-258">Catalog</span></span>  
  
|<span data-ttu-id="2246d-259">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-259">ColumnName</span></span>|<span data-ttu-id="2246d-260">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-261">CATALOG_NAME</span></span>|<span data-ttu-id="2246d-262">String</span><span class="sxs-lookup"><span data-stu-id="2246d-262">String</span></span>|  
|<span data-ttu-id="2246d-263">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-263">DESCRIPTION</span></span>|<span data-ttu-id="2246d-264">String</span><span class="sxs-lookup"><span data-stu-id="2246d-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2246d-265">Indeksy</span><span class="sxs-lookup"><span data-stu-id="2246d-265">Indexes</span></span>  
  
|<span data-ttu-id="2246d-266">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-266">ColumnName</span></span>|<span data-ttu-id="2246d-267">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-268">TABLE_CATALOG</span></span>|<span data-ttu-id="2246d-269">String</span><span class="sxs-lookup"><span data-stu-id="2246d-269">String</span></span>|  
|<span data-ttu-id="2246d-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="2246d-271">String</span><span class="sxs-lookup"><span data-stu-id="2246d-271">String</span></span>|  
|<span data-ttu-id="2246d-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-272">TABLE_NAME</span></span>|<span data-ttu-id="2246d-273">String</span><span class="sxs-lookup"><span data-stu-id="2246d-273">String</span></span>|  
|<span data-ttu-id="2246d-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-274">INDEX_CATALOG</span></span>|<span data-ttu-id="2246d-275">String</span><span class="sxs-lookup"><span data-stu-id="2246d-275">String</span></span>|  
|<span data-ttu-id="2246d-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="2246d-277">String</span><span class="sxs-lookup"><span data-stu-id="2246d-277">String</span></span>|  
|<span data-ttu-id="2246d-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-278">INDEX_NAME</span></span>|<span data-ttu-id="2246d-279">String</span><span class="sxs-lookup"><span data-stu-id="2246d-279">String</span></span>|  
|<span data-ttu-id="2246d-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2246d-280">PRIMARY_KEY</span></span>|<span data-ttu-id="2246d-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-281">Boolean</span></span>|  
|<span data-ttu-id="2246d-282">UNIKATOWY</span><span class="sxs-lookup"><span data-stu-id="2246d-282">UNIQUE</span></span>|<span data-ttu-id="2246d-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-283">Boolean</span></span>|  
|<span data-ttu-id="2246d-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2246d-284">CLUSTERED</span></span>|<span data-ttu-id="2246d-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-285">Boolean</span></span>|  
|<span data-ttu-id="2246d-286">TYP</span><span class="sxs-lookup"><span data-stu-id="2246d-286">TYPE</span></span>|<span data-ttu-id="2246d-287">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-287">Int32</span></span>|  
|<span data-ttu-id="2246d-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2246d-288">FILL_FACTOR</span></span>|<span data-ttu-id="2246d-289">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-289">Int32</span></span>|  
|<span data-ttu-id="2246d-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2246d-290">INITIAL_SIZE</span></span>|<span data-ttu-id="2246d-291">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-291">Int32</span></span>|  
|<span data-ttu-id="2246d-292">NULL — Wartości</span><span class="sxs-lookup"><span data-stu-id="2246d-292">NULLS</span></span>|<span data-ttu-id="2246d-293">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-293">Int32</span></span>|  
|<span data-ttu-id="2246d-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2246d-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2246d-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-295">Boolean</span></span>|  
|<span data-ttu-id="2246d-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2246d-296">AUTO_UPDATE</span></span>|<span data-ttu-id="2246d-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-297">Boolean</span></span>|  
|<span data-ttu-id="2246d-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2246d-298">NULL_COLLATION</span></span>|<span data-ttu-id="2246d-299">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-299">Int32</span></span>|  
|<span data-ttu-id="2246d-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2246d-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="2246d-301">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-301">Int64</span></span>|  
|<span data-ttu-id="2246d-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-302">COLUMN_NAME</span></span>|<span data-ttu-id="2246d-303">String</span><span class="sxs-lookup"><span data-stu-id="2246d-303">String</span></span>|  
|<span data-ttu-id="2246d-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-304">COLUMN_GUID</span></span>|<span data-ttu-id="2246d-305">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-305">Guid</span></span>|  
|<span data-ttu-id="2246d-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2246d-306">COLUMN_PROPID</span></span>|<span data-ttu-id="2246d-307">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-307">Int64</span></span>|  
|<span data-ttu-id="2246d-308">SORTOWANIE</span><span class="sxs-lookup"><span data-stu-id="2246d-308">COLLATION</span></span>|<span data-ttu-id="2246d-309">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-309">Int16</span></span>|  
|<span data-ttu-id="2246d-310">KARDYNALNOŚCI</span><span class="sxs-lookup"><span data-stu-id="2246d-310">CARDINALITY</span></span>|<span data-ttu-id="2246d-311">Liczba dziesiętna</span><span class="sxs-lookup"><span data-stu-id="2246d-311">Decimal</span></span>|  
|<span data-ttu-id="2246d-312">Page</span><span class="sxs-lookup"><span data-stu-id="2246d-312">PAGES</span></span>|<span data-ttu-id="2246d-313">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-313">Int32</span></span>|  
|<span data-ttu-id="2246d-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2246d-314">FILTER_CONDITION</span></span>|<span data-ttu-id="2246d-315">String</span><span class="sxs-lookup"><span data-stu-id="2246d-315">String</span></span>|  
|<span data-ttu-id="2246d-316">ZINTEGROWANE</span><span class="sxs-lookup"><span data-stu-id="2246d-316">INTEGRATED</span></span>|<span data-ttu-id="2246d-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="2246d-318">Dostawca OLE DB Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="2246d-318">Microsoft Oracle OLE DB Provider</span></span>  

 <span data-ttu-id="2246d-319">Sterownik programu Microsoft Oracle OLE DB obsługuje następujące wybrane kolekcje schematów oprócz wspólnych kolekcji schematów:</span><span class="sxs-lookup"><span data-stu-id="2246d-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="2246d-320">Tabele</span><span class="sxs-lookup"><span data-stu-id="2246d-320">Tables</span></span>  
  
- <span data-ttu-id="2246d-321">Kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-321">Columns</span></span>  
  
- <span data-ttu-id="2246d-322">Procedury</span><span class="sxs-lookup"><span data-stu-id="2246d-322">Procedures</span></span>  
  
- <span data-ttu-id="2246d-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2246d-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="2246d-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2246d-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="2246d-325">Widoki</span><span class="sxs-lookup"><span data-stu-id="2246d-325">Views</span></span>  
  
- <span data-ttu-id="2246d-326">Indeksy</span><span class="sxs-lookup"><span data-stu-id="2246d-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2246d-327">Tabele</span><span class="sxs-lookup"><span data-stu-id="2246d-327">Tables</span></span>  
  
|<span data-ttu-id="2246d-328">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-328">ColumnName</span></span>|<span data-ttu-id="2246d-329">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-330">TABLE_CATALOG</span></span>|<span data-ttu-id="2246d-331">String</span><span class="sxs-lookup"><span data-stu-id="2246d-331">String</span></span>|  
|<span data-ttu-id="2246d-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="2246d-333">String</span><span class="sxs-lookup"><span data-stu-id="2246d-333">String</span></span>|  
|<span data-ttu-id="2246d-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-334">TABLE_NAME</span></span>|<span data-ttu-id="2246d-335">String</span><span class="sxs-lookup"><span data-stu-id="2246d-335">String</span></span>|  
|<span data-ttu-id="2246d-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-336">TABLE_TYPE</span></span>|<span data-ttu-id="2246d-337">String</span><span class="sxs-lookup"><span data-stu-id="2246d-337">String</span></span>|  
|<span data-ttu-id="2246d-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-338">TABLE_GUID</span></span>|<span data-ttu-id="2246d-339">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-339">Guid</span></span>|  
|<span data-ttu-id="2246d-340">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-340">DESCRIPTION</span></span>|<span data-ttu-id="2246d-341">String</span><span class="sxs-lookup"><span data-stu-id="2246d-341">String</span></span>|  
|<span data-ttu-id="2246d-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2246d-342">TABLE_PROPID</span></span>|<span data-ttu-id="2246d-343">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-343">Int64</span></span>|  
|<span data-ttu-id="2246d-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2246d-344">DATE_CREATED</span></span>|<span data-ttu-id="2246d-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-345">DateTime</span></span>|  
|<span data-ttu-id="2246d-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2246d-346">DATE_MODIFIED</span></span>|<span data-ttu-id="2246d-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2246d-348">Kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-348">Columns</span></span>  
  
|<span data-ttu-id="2246d-349">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-349">ColumnName</span></span>|<span data-ttu-id="2246d-350">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-351">TABLE_CATALOG</span></span>|<span data-ttu-id="2246d-352">String</span><span class="sxs-lookup"><span data-stu-id="2246d-352">String</span></span>|  
|<span data-ttu-id="2246d-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="2246d-354">String</span><span class="sxs-lookup"><span data-stu-id="2246d-354">String</span></span>|  
|<span data-ttu-id="2246d-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-355">TABLE_NAME</span></span>|<span data-ttu-id="2246d-356">String</span><span class="sxs-lookup"><span data-stu-id="2246d-356">String</span></span>|  
|<span data-ttu-id="2246d-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-357">COLUMN_NAME</span></span>|<span data-ttu-id="2246d-358">String</span><span class="sxs-lookup"><span data-stu-id="2246d-358">String</span></span>|  
|<span data-ttu-id="2246d-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-359">COLUMN_GUID</span></span>|<span data-ttu-id="2246d-360">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-360">Guid</span></span>|  
|<span data-ttu-id="2246d-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2246d-361">COLUMN_PROPID</span></span>|<span data-ttu-id="2246d-362">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-362">Int64</span></span>|  
|<span data-ttu-id="2246d-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2246d-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="2246d-364">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-364">Int64</span></span>|  
|<span data-ttu-id="2246d-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2246d-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2246d-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-366">Boolean</span></span>|  
|<span data-ttu-id="2246d-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2246d-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2246d-368">String</span><span class="sxs-lookup"><span data-stu-id="2246d-368">String</span></span>|  
|<span data-ttu-id="2246d-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2246d-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="2246d-370">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-370">Int64</span></span>|  
|<span data-ttu-id="2246d-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2246d-371">IS_NULLABLE</span></span>|<span data-ttu-id="2246d-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-372">Boolean</span></span>|  
|<span data-ttu-id="2246d-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-373">DATA_TYPE</span></span>|<span data-ttu-id="2246d-374">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-374">Int32</span></span>|  
|<span data-ttu-id="2246d-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-375">TYPE_GUID</span></span>|<span data-ttu-id="2246d-376">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-376">Guid</span></span>|  
|<span data-ttu-id="2246d-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2246d-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2246d-378">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-378">Int64</span></span>|  
|<span data-ttu-id="2246d-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2246d-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2246d-380">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-380">Int64</span></span>|  
|<span data-ttu-id="2246d-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2246d-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2246d-382">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-382">Int32</span></span>|  
|<span data-ttu-id="2246d-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2246d-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="2246d-384">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-384">Int16</span></span>|  
|<span data-ttu-id="2246d-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2246d-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="2246d-386">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-386">Int64</span></span>|  
|<span data-ttu-id="2246d-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2246d-388">String</span><span class="sxs-lookup"><span data-stu-id="2246d-388">String</span></span>|  
|<span data-ttu-id="2246d-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2246d-390">String</span><span class="sxs-lookup"><span data-stu-id="2246d-390">String</span></span>|  
|<span data-ttu-id="2246d-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2246d-392">String</span><span class="sxs-lookup"><span data-stu-id="2246d-392">String</span></span>|  
|<span data-ttu-id="2246d-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="2246d-394">String</span><span class="sxs-lookup"><span data-stu-id="2246d-394">String</span></span>|  
|<span data-ttu-id="2246d-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2246d-396">String</span><span class="sxs-lookup"><span data-stu-id="2246d-396">String</span></span>|  
|<span data-ttu-id="2246d-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-397">COLLATION_NAME</span></span>|<span data-ttu-id="2246d-398">String</span><span class="sxs-lookup"><span data-stu-id="2246d-398">String</span></span>|  
|<span data-ttu-id="2246d-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2246d-400">String</span><span class="sxs-lookup"><span data-stu-id="2246d-400">String</span></span>|  
|<span data-ttu-id="2246d-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2246d-402">String</span><span class="sxs-lookup"><span data-stu-id="2246d-402">String</span></span>|  
|<span data-ttu-id="2246d-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-403">DOMAIN_NAME</span></span>|<span data-ttu-id="2246d-404">String</span><span class="sxs-lookup"><span data-stu-id="2246d-404">String</span></span>|  
|<span data-ttu-id="2246d-405">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-405">DESCRIPTION</span></span>|<span data-ttu-id="2246d-406">String</span><span class="sxs-lookup"><span data-stu-id="2246d-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2246d-407">Procedury</span><span class="sxs-lookup"><span data-stu-id="2246d-407">Procedures</span></span>  
  
|<span data-ttu-id="2246d-408">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-408">ColumnName</span></span>|<span data-ttu-id="2246d-409">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2246d-411">String</span><span class="sxs-lookup"><span data-stu-id="2246d-411">String</span></span>|  
|<span data-ttu-id="2246d-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2246d-413">String</span><span class="sxs-lookup"><span data-stu-id="2246d-413">String</span></span>|  
|<span data-ttu-id="2246d-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="2246d-415">String</span><span class="sxs-lookup"><span data-stu-id="2246d-415">String</span></span>|  
|<span data-ttu-id="2246d-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2246d-417">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-417">Int16</span></span>|  
|<span data-ttu-id="2246d-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2246d-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2246d-419">String</span><span class="sxs-lookup"><span data-stu-id="2246d-419">String</span></span>|  
|<span data-ttu-id="2246d-420">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-420">DESCRIPTION</span></span>|<span data-ttu-id="2246d-421">String</span><span class="sxs-lookup"><span data-stu-id="2246d-421">String</span></span>|  
|<span data-ttu-id="2246d-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2246d-422">DATE_CREATED</span></span>|<span data-ttu-id="2246d-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-423">DateTime</span></span>|  
|<span data-ttu-id="2246d-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2246d-424">DATE_MODIFIED</span></span>|<span data-ttu-id="2246d-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="2246d-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2246d-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="2246d-427">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-427">ColumnName</span></span>|<span data-ttu-id="2246d-428">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2246d-430">String</span><span class="sxs-lookup"><span data-stu-id="2246d-430">String</span></span>|  
|<span data-ttu-id="2246d-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2246d-432">String</span><span class="sxs-lookup"><span data-stu-id="2246d-432">String</span></span>|  
|<span data-ttu-id="2246d-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="2246d-434">String</span><span class="sxs-lookup"><span data-stu-id="2246d-434">String</span></span>|  
|<span data-ttu-id="2246d-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-435">COLUMN_NAME</span></span>|<span data-ttu-id="2246d-436">String</span><span class="sxs-lookup"><span data-stu-id="2246d-436">String</span></span>|  
|<span data-ttu-id="2246d-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-437">COLUMN_GUID</span></span>|<span data-ttu-id="2246d-438">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-438">Guid</span></span>|  
|<span data-ttu-id="2246d-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2246d-439">COLUMN_PROPID</span></span>|<span data-ttu-id="2246d-440">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-440">Int64</span></span>|  
|<span data-ttu-id="2246d-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="2246d-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="2246d-442">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-442">Int64</span></span>|  
|<span data-ttu-id="2246d-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2246d-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="2246d-444">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-444">Int64</span></span>|  
|<span data-ttu-id="2246d-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2246d-445">IS_NULLABLE</span></span>|<span data-ttu-id="2246d-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-446">Boolean</span></span>|  
|<span data-ttu-id="2246d-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-447">DATA_TYPE</span></span>|<span data-ttu-id="2246d-448">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-448">Int32</span></span>|  
|<span data-ttu-id="2246d-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-449">TYPE_GUID</span></span>|<span data-ttu-id="2246d-450">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-450">Guid</span></span>|  
|<span data-ttu-id="2246d-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2246d-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2246d-452">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-452">Int64</span></span>|  
|<span data-ttu-id="2246d-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2246d-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2246d-454">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-454">Int64</span></span>|  
|<span data-ttu-id="2246d-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2246d-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2246d-456">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-456">Int32</span></span>|  
|<span data-ttu-id="2246d-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2246d-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="2246d-458">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-458">Int16</span></span>|  
|<span data-ttu-id="2246d-459">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-459">DESCRIPTION</span></span>|<span data-ttu-id="2246d-460">String</span><span class="sxs-lookup"><span data-stu-id="2246d-460">String</span></span>|  
|<span data-ttu-id="2246d-461">WYSTĘPUJĄ</span><span class="sxs-lookup"><span data-stu-id="2246d-461">OVERLOAD</span></span>|<span data-ttu-id="2246d-462">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="2246d-463">Widoki</span><span class="sxs-lookup"><span data-stu-id="2246d-463">Views</span></span>  
  
|<span data-ttu-id="2246d-464">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-464">ColumnName</span></span>|<span data-ttu-id="2246d-465">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-466">TABLE_CATALOG</span></span>|<span data-ttu-id="2246d-467">String</span><span class="sxs-lookup"><span data-stu-id="2246d-467">String</span></span>|  
|<span data-ttu-id="2246d-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="2246d-469">String</span><span class="sxs-lookup"><span data-stu-id="2246d-469">String</span></span>|  
|<span data-ttu-id="2246d-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-470">TABLE_NAME</span></span>|<span data-ttu-id="2246d-471">String</span><span class="sxs-lookup"><span data-stu-id="2246d-471">String</span></span>|  
|<span data-ttu-id="2246d-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2246d-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="2246d-473">String</span><span class="sxs-lookup"><span data-stu-id="2246d-473">String</span></span>|  
|<span data-ttu-id="2246d-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="2246d-474">CHECK_OPTION</span></span>|<span data-ttu-id="2246d-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-475">Boolean</span></span>|  
|<span data-ttu-id="2246d-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="2246d-476">IS_UPDATABLE</span></span>|<span data-ttu-id="2246d-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-477">Boolean</span></span>|  
|<span data-ttu-id="2246d-478">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-478">DESCRIPTION</span></span>|<span data-ttu-id="2246d-479">String</span><span class="sxs-lookup"><span data-stu-id="2246d-479">String</span></span>|  
|<span data-ttu-id="2246d-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2246d-480">DATE_CREATED</span></span>|<span data-ttu-id="2246d-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-481">DateTime</span></span>|  
|<span data-ttu-id="2246d-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2246d-482">DATE_MODIFIED</span></span>|<span data-ttu-id="2246d-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2246d-484">Indeksy</span><span class="sxs-lookup"><span data-stu-id="2246d-484">Indexes</span></span>  
  
|<span data-ttu-id="2246d-485">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-485">ColumnName</span></span>|<span data-ttu-id="2246d-486">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-487">TABLE_CATALOG</span></span>|<span data-ttu-id="2246d-488">String</span><span class="sxs-lookup"><span data-stu-id="2246d-488">String</span></span>|  
|<span data-ttu-id="2246d-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="2246d-490">String</span><span class="sxs-lookup"><span data-stu-id="2246d-490">String</span></span>|  
|<span data-ttu-id="2246d-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-491">TABLE_NAME</span></span>|<span data-ttu-id="2246d-492">String</span><span class="sxs-lookup"><span data-stu-id="2246d-492">String</span></span>|  
|<span data-ttu-id="2246d-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-493">INDEX_CATALOG</span></span>|<span data-ttu-id="2246d-494">String</span><span class="sxs-lookup"><span data-stu-id="2246d-494">String</span></span>|  
|<span data-ttu-id="2246d-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="2246d-496">String</span><span class="sxs-lookup"><span data-stu-id="2246d-496">String</span></span>|  
|<span data-ttu-id="2246d-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-497">INDEX_NAME</span></span>|<span data-ttu-id="2246d-498">String</span><span class="sxs-lookup"><span data-stu-id="2246d-498">String</span></span>|  
|<span data-ttu-id="2246d-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2246d-499">PRIMARY_KEY</span></span>|<span data-ttu-id="2246d-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-500">Boolean</span></span>|  
|<span data-ttu-id="2246d-501">UNIKATOWY</span><span class="sxs-lookup"><span data-stu-id="2246d-501">UNIQUE</span></span>|<span data-ttu-id="2246d-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-502">Boolean</span></span>|  
|<span data-ttu-id="2246d-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2246d-503">CLUSTERED</span></span>|<span data-ttu-id="2246d-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-504">Boolean</span></span>|  
|<span data-ttu-id="2246d-505">TYP</span><span class="sxs-lookup"><span data-stu-id="2246d-505">TYPE</span></span>|<span data-ttu-id="2246d-506">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-506">Int32</span></span>|  
|<span data-ttu-id="2246d-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2246d-507">FILL_FACTOR</span></span>|<span data-ttu-id="2246d-508">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-508">Int32</span></span>|  
|<span data-ttu-id="2246d-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2246d-509">INITIAL_SIZE</span></span>|<span data-ttu-id="2246d-510">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-510">Int32</span></span>|  
|<span data-ttu-id="2246d-511">NULL — Wartości</span><span class="sxs-lookup"><span data-stu-id="2246d-511">NULLS</span></span>|<span data-ttu-id="2246d-512">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-512">Int32</span></span>|  
|<span data-ttu-id="2246d-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2246d-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2246d-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-514">Boolean</span></span>|  
|<span data-ttu-id="2246d-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2246d-515">AUTO_UPDATE</span></span>|<span data-ttu-id="2246d-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-516">Boolean</span></span>|  
|<span data-ttu-id="2246d-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2246d-517">NULL_COLLATION</span></span>|<span data-ttu-id="2246d-518">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-518">Int32</span></span>|  
|<span data-ttu-id="2246d-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2246d-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="2246d-520">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-520">Int64</span></span>|  
|<span data-ttu-id="2246d-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-521">COLUMN_NAME</span></span>|<span data-ttu-id="2246d-522">String</span><span class="sxs-lookup"><span data-stu-id="2246d-522">String</span></span>|  
|<span data-ttu-id="2246d-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-523">COLUMN_GUID</span></span>|<span data-ttu-id="2246d-524">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-524">Guid</span></span>|  
|<span data-ttu-id="2246d-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2246d-525">COLUMN_PROPID</span></span>|<span data-ttu-id="2246d-526">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-526">Int64</span></span>|  
|<span data-ttu-id="2246d-527">SORTOWANIE</span><span class="sxs-lookup"><span data-stu-id="2246d-527">COLLATION</span></span>|<span data-ttu-id="2246d-528">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-528">Int16</span></span>|  
|<span data-ttu-id="2246d-529">KARDYNALNOŚCI</span><span class="sxs-lookup"><span data-stu-id="2246d-529">CARDINALITY</span></span>|<span data-ttu-id="2246d-530">Liczba dziesiętna</span><span class="sxs-lookup"><span data-stu-id="2246d-530">Decimal</span></span>|  
|<span data-ttu-id="2246d-531">Page</span><span class="sxs-lookup"><span data-stu-id="2246d-531">PAGES</span></span>|<span data-ttu-id="2246d-532">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-532">Int32</span></span>|  
|<span data-ttu-id="2246d-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2246d-533">FILTER_CONDITION</span></span>|<span data-ttu-id="2246d-534">String</span><span class="sxs-lookup"><span data-stu-id="2246d-534">String</span></span>|  
|<span data-ttu-id="2246d-535">ZINTEGROWANE</span><span class="sxs-lookup"><span data-stu-id="2246d-535">INTEGRATED</span></span>|<span data-ttu-id="2246d-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="2246d-537">Dostawca OLE DB Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="2246d-537">Microsoft Jet OLE DB Provider</span></span>  

 <span data-ttu-id="2246d-538">Sterownik programu Microsoft Jet OLE DB obsługuje następujące kolekcje schematów oprócz wspólnych kolekcji schematów:</span><span class="sxs-lookup"><span data-stu-id="2246d-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="2246d-539">Tabele</span><span class="sxs-lookup"><span data-stu-id="2246d-539">Tables</span></span>  
  
- <span data-ttu-id="2246d-540">Kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-540">Columns</span></span>  
  
- <span data-ttu-id="2246d-541">Procedury</span><span class="sxs-lookup"><span data-stu-id="2246d-541">Procedures</span></span>  
  
- <span data-ttu-id="2246d-542">Widoki</span><span class="sxs-lookup"><span data-stu-id="2246d-542">Views</span></span>  
  
- <span data-ttu-id="2246d-543">Indeksy</span><span class="sxs-lookup"><span data-stu-id="2246d-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2246d-544">Tabele</span><span class="sxs-lookup"><span data-stu-id="2246d-544">Tables</span></span>  
  
|<span data-ttu-id="2246d-545">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-545">ColumnName</span></span>|<span data-ttu-id="2246d-546">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-547">TABLE_CATALOG</span></span>|<span data-ttu-id="2246d-548">String</span><span class="sxs-lookup"><span data-stu-id="2246d-548">String</span></span>|  
|<span data-ttu-id="2246d-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="2246d-550">String</span><span class="sxs-lookup"><span data-stu-id="2246d-550">String</span></span>|  
|<span data-ttu-id="2246d-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-551">TABLE_NAME</span></span>|<span data-ttu-id="2246d-552">String</span><span class="sxs-lookup"><span data-stu-id="2246d-552">String</span></span>|  
|<span data-ttu-id="2246d-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-553">TABLE_TYPE</span></span>|<span data-ttu-id="2246d-554">String</span><span class="sxs-lookup"><span data-stu-id="2246d-554">String</span></span>|  
|<span data-ttu-id="2246d-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-555">TABLE_GUID</span></span>|<span data-ttu-id="2246d-556">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-556">Guid</span></span>|  
|<span data-ttu-id="2246d-557">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-557">DESCRIPTION</span></span>|<span data-ttu-id="2246d-558">String</span><span class="sxs-lookup"><span data-stu-id="2246d-558">String</span></span>|  
|<span data-ttu-id="2246d-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2246d-559">TABLE_PROPID</span></span>|<span data-ttu-id="2246d-560">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-560">Int64</span></span>|  
|<span data-ttu-id="2246d-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2246d-561">DATE_CREATED</span></span>|<span data-ttu-id="2246d-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-562">DateTime</span></span>|  
|<span data-ttu-id="2246d-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2246d-563">DATE_MODIFIED</span></span>|<span data-ttu-id="2246d-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2246d-565">Kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-565">Columns</span></span>  
  
|<span data-ttu-id="2246d-566">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-566">ColumnName</span></span>|<span data-ttu-id="2246d-567">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-568">TABLE_CATALOG</span></span>|<span data-ttu-id="2246d-569">String</span><span class="sxs-lookup"><span data-stu-id="2246d-569">String</span></span>|  
|<span data-ttu-id="2246d-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="2246d-571">String</span><span class="sxs-lookup"><span data-stu-id="2246d-571">String</span></span>|  
|<span data-ttu-id="2246d-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-572">TABLE_NAME</span></span>|<span data-ttu-id="2246d-573">String</span><span class="sxs-lookup"><span data-stu-id="2246d-573">String</span></span>|  
|<span data-ttu-id="2246d-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-574">COLUMN_NAME</span></span>|<span data-ttu-id="2246d-575">String</span><span class="sxs-lookup"><span data-stu-id="2246d-575">String</span></span>|  
|<span data-ttu-id="2246d-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-576">COLUMN_GUID</span></span>|<span data-ttu-id="2246d-577">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-577">Guid</span></span>|  
|<span data-ttu-id="2246d-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2246d-578">COLUMN_PROPID</span></span>|<span data-ttu-id="2246d-579">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-579">Int64</span></span>|  
|<span data-ttu-id="2246d-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2246d-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="2246d-581">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-581">Int64</span></span>|  
|<span data-ttu-id="2246d-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2246d-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2246d-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-583">Boolean</span></span>|  
|<span data-ttu-id="2246d-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2246d-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2246d-585">String</span><span class="sxs-lookup"><span data-stu-id="2246d-585">String</span></span>|  
|<span data-ttu-id="2246d-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2246d-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="2246d-587">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-587">Int64</span></span>|  
|<span data-ttu-id="2246d-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2246d-588">IS_NULLABLE</span></span>|<span data-ttu-id="2246d-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-589">Boolean</span></span>|  
|<span data-ttu-id="2246d-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-590">DATA_TYPE</span></span>|<span data-ttu-id="2246d-591">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-591">Int32</span></span>|  
|<span data-ttu-id="2246d-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-592">TYPE_GUID</span></span>|<span data-ttu-id="2246d-593">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-593">Guid</span></span>|  
|<span data-ttu-id="2246d-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2246d-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2246d-595">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-595">Int64</span></span>|  
|<span data-ttu-id="2246d-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2246d-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2246d-597">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-597">Int64</span></span>|  
|<span data-ttu-id="2246d-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2246d-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2246d-599">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-599">Int32</span></span>|  
|<span data-ttu-id="2246d-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2246d-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="2246d-601">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-601">Int16</span></span>|  
|<span data-ttu-id="2246d-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2246d-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="2246d-603">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-603">Int64</span></span>|  
|<span data-ttu-id="2246d-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2246d-605">String</span><span class="sxs-lookup"><span data-stu-id="2246d-605">String</span></span>|  
|<span data-ttu-id="2246d-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2246d-607">String</span><span class="sxs-lookup"><span data-stu-id="2246d-607">String</span></span>|  
|<span data-ttu-id="2246d-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2246d-609">String</span><span class="sxs-lookup"><span data-stu-id="2246d-609">String</span></span>|  
|<span data-ttu-id="2246d-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="2246d-611">String</span><span class="sxs-lookup"><span data-stu-id="2246d-611">String</span></span>|  
|<span data-ttu-id="2246d-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2246d-613">String</span><span class="sxs-lookup"><span data-stu-id="2246d-613">String</span></span>|  
|<span data-ttu-id="2246d-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-614">COLLATION_NAME</span></span>|<span data-ttu-id="2246d-615">String</span><span class="sxs-lookup"><span data-stu-id="2246d-615">String</span></span>|  
|<span data-ttu-id="2246d-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2246d-617">String</span><span class="sxs-lookup"><span data-stu-id="2246d-617">String</span></span>|  
|<span data-ttu-id="2246d-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2246d-619">String</span><span class="sxs-lookup"><span data-stu-id="2246d-619">String</span></span>|  
|<span data-ttu-id="2246d-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-620">DOMAIN_NAME</span></span>|<span data-ttu-id="2246d-621">String</span><span class="sxs-lookup"><span data-stu-id="2246d-621">String</span></span>|  
|<span data-ttu-id="2246d-622">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-622">DESCRIPTION</span></span>|<span data-ttu-id="2246d-623">String</span><span class="sxs-lookup"><span data-stu-id="2246d-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2246d-624">Procedury</span><span class="sxs-lookup"><span data-stu-id="2246d-624">Procedures</span></span>  
  
|<span data-ttu-id="2246d-625">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-625">ColumnName</span></span>|<span data-ttu-id="2246d-626">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2246d-628">String</span><span class="sxs-lookup"><span data-stu-id="2246d-628">String</span></span>|  
|<span data-ttu-id="2246d-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2246d-630">String</span><span class="sxs-lookup"><span data-stu-id="2246d-630">String</span></span>|  
|<span data-ttu-id="2246d-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="2246d-632">String</span><span class="sxs-lookup"><span data-stu-id="2246d-632">String</span></span>|  
|<span data-ttu-id="2246d-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2246d-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2246d-634">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-634">Int16</span></span>|  
|<span data-ttu-id="2246d-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2246d-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2246d-636">String</span><span class="sxs-lookup"><span data-stu-id="2246d-636">String</span></span>|  
|<span data-ttu-id="2246d-637">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-637">DESCRIPTION</span></span>|<span data-ttu-id="2246d-638">String</span><span class="sxs-lookup"><span data-stu-id="2246d-638">String</span></span>|  
|<span data-ttu-id="2246d-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2246d-639">DATE_CREATED</span></span>|<span data-ttu-id="2246d-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-640">DateTime</span></span>|  
|<span data-ttu-id="2246d-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2246d-641">DATE_MODIFIED</span></span>|<span data-ttu-id="2246d-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="2246d-643">Widoki</span><span class="sxs-lookup"><span data-stu-id="2246d-643">Views</span></span>  
  
|<span data-ttu-id="2246d-644">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-644">ColumnName</span></span>|<span data-ttu-id="2246d-645">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-646">TABLE_CATALOG</span></span>|<span data-ttu-id="2246d-647">String</span><span class="sxs-lookup"><span data-stu-id="2246d-647">String</span></span>|  
|<span data-ttu-id="2246d-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="2246d-649">String</span><span class="sxs-lookup"><span data-stu-id="2246d-649">String</span></span>|  
|<span data-ttu-id="2246d-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-650">TABLE_NAME</span></span>|<span data-ttu-id="2246d-651">String</span><span class="sxs-lookup"><span data-stu-id="2246d-651">String</span></span>|  
|<span data-ttu-id="2246d-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2246d-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="2246d-653">String</span><span class="sxs-lookup"><span data-stu-id="2246d-653">String</span></span>|  
|<span data-ttu-id="2246d-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="2246d-654">CHECK_OPTION</span></span>|<span data-ttu-id="2246d-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-655">Boolean</span></span>|  
|<span data-ttu-id="2246d-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="2246d-656">IS_UPDATABLE</span></span>|<span data-ttu-id="2246d-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-657">Boolean</span></span>|  
|<span data-ttu-id="2246d-658">OPIS</span><span class="sxs-lookup"><span data-stu-id="2246d-658">DESCRIPTION</span></span>|<span data-ttu-id="2246d-659">String</span><span class="sxs-lookup"><span data-stu-id="2246d-659">String</span></span>|  
|<span data-ttu-id="2246d-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2246d-660">DATE_CREATED</span></span>|<span data-ttu-id="2246d-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-661">DateTime</span></span>|  
|<span data-ttu-id="2246d-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2246d-662">DATE_MODIFIED</span></span>|<span data-ttu-id="2246d-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="2246d-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2246d-664">Indeksy</span><span class="sxs-lookup"><span data-stu-id="2246d-664">Indexes</span></span>  
  
|<span data-ttu-id="2246d-665">nazwa_kolumny</span><span class="sxs-lookup"><span data-stu-id="2246d-665">ColumnName</span></span>|<span data-ttu-id="2246d-666">typ_danych</span><span class="sxs-lookup"><span data-stu-id="2246d-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2246d-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-667">TABLE_CATALOG</span></span>|<span data-ttu-id="2246d-668">String</span><span class="sxs-lookup"><span data-stu-id="2246d-668">String</span></span>|  
|<span data-ttu-id="2246d-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="2246d-670">String</span><span class="sxs-lookup"><span data-stu-id="2246d-670">String</span></span>|  
|<span data-ttu-id="2246d-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-671">TABLE_NAME</span></span>|<span data-ttu-id="2246d-672">String</span><span class="sxs-lookup"><span data-stu-id="2246d-672">String</span></span>|  
|<span data-ttu-id="2246d-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2246d-673">INDEX_CATALOG</span></span>|<span data-ttu-id="2246d-674">String</span><span class="sxs-lookup"><span data-stu-id="2246d-674">String</span></span>|  
|<span data-ttu-id="2246d-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2246d-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="2246d-676">String</span><span class="sxs-lookup"><span data-stu-id="2246d-676">String</span></span>|  
|<span data-ttu-id="2246d-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-677">INDEX_NAME</span></span>|<span data-ttu-id="2246d-678">String</span><span class="sxs-lookup"><span data-stu-id="2246d-678">String</span></span>|  
|<span data-ttu-id="2246d-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2246d-679">PRIMARY_KEY</span></span>|<span data-ttu-id="2246d-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-680">Boolean</span></span>|  
|<span data-ttu-id="2246d-681">UNIKATOWY</span><span class="sxs-lookup"><span data-stu-id="2246d-681">UNIQUE</span></span>|<span data-ttu-id="2246d-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-682">Boolean</span></span>|  
|<span data-ttu-id="2246d-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2246d-683">CLUSTERED</span></span>|<span data-ttu-id="2246d-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-684">Boolean</span></span>|  
|<span data-ttu-id="2246d-685">TYP</span><span class="sxs-lookup"><span data-stu-id="2246d-685">TYPE</span></span>|<span data-ttu-id="2246d-686">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-686">Int32</span></span>|  
|<span data-ttu-id="2246d-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2246d-687">FILL_FACTOR</span></span>|<span data-ttu-id="2246d-688">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-688">Int32</span></span>|  
|<span data-ttu-id="2246d-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2246d-689">INITIAL_SIZE</span></span>|<span data-ttu-id="2246d-690">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-690">Int32</span></span>|  
|<span data-ttu-id="2246d-691">NULL — Wartości</span><span class="sxs-lookup"><span data-stu-id="2246d-691">NULLS</span></span>|<span data-ttu-id="2246d-692">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-692">Int32</span></span>|  
|<span data-ttu-id="2246d-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2246d-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2246d-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-694">Boolean</span></span>|  
|<span data-ttu-id="2246d-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2246d-695">AUTO_UPDATE</span></span>|<span data-ttu-id="2246d-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-696">Boolean</span></span>|  
|<span data-ttu-id="2246d-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2246d-697">NULL_COLLATION</span></span>|<span data-ttu-id="2246d-698">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-698">Int32</span></span>|  
|<span data-ttu-id="2246d-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2246d-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="2246d-700">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-700">Int64</span></span>|  
|<span data-ttu-id="2246d-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2246d-701">COLUMN_NAME</span></span>|<span data-ttu-id="2246d-702">String</span><span class="sxs-lookup"><span data-stu-id="2246d-702">String</span></span>|  
|<span data-ttu-id="2246d-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2246d-703">COLUMN_GUID</span></span>|<span data-ttu-id="2246d-704">Guid (identyfikator GUID)</span><span class="sxs-lookup"><span data-stu-id="2246d-704">Guid</span></span>|  
|<span data-ttu-id="2246d-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2246d-705">COLUMN_PROPID</span></span>|<span data-ttu-id="2246d-706">Int64</span><span class="sxs-lookup"><span data-stu-id="2246d-706">Int64</span></span>|  
|<span data-ttu-id="2246d-707">SORTOWANIE</span><span class="sxs-lookup"><span data-stu-id="2246d-707">COLLATION</span></span>|<span data-ttu-id="2246d-708">Int16</span><span class="sxs-lookup"><span data-stu-id="2246d-708">Int16</span></span>|  
|<span data-ttu-id="2246d-709">KARDYNALNOŚCI</span><span class="sxs-lookup"><span data-stu-id="2246d-709">CARDINALITY</span></span>|<span data-ttu-id="2246d-710">Liczba dziesiętna</span><span class="sxs-lookup"><span data-stu-id="2246d-710">Decimal</span></span>|  
|<span data-ttu-id="2246d-711">Page</span><span class="sxs-lookup"><span data-stu-id="2246d-711">PAGES</span></span>|<span data-ttu-id="2246d-712">Int32</span><span class="sxs-lookup"><span data-stu-id="2246d-712">Int32</span></span>|  
|<span data-ttu-id="2246d-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2246d-713">FILTER_CONDITION</span></span>|<span data-ttu-id="2246d-714">String</span><span class="sxs-lookup"><span data-stu-id="2246d-714">String</span></span>|  
|<span data-ttu-id="2246d-715">ZINTEGROWANE</span><span class="sxs-lookup"><span data-stu-id="2246d-715">INTEGRATED</span></span>|<span data-ttu-id="2246d-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="2246d-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2246d-717">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2246d-717">See also</span></span>

- [<span data-ttu-id="2246d-718">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2246d-718">ADO.NET Overview</span></span>](ado-net-overview.md)
