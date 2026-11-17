# Gate-IN-OUT
Vehicle entry record
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <meta name="mobile-web-app-capable" content="yes" />
  <meta name="apple-mobile-web-app-capable" content="yes" />
  <meta name="theme-color" content="#0f172a" />
  <title>Satvik Crunch Factory — Mobile Gate Register</title>
  <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Crect width='100' height='100' rx='22' fill='%23ea580c'/%3E%3Ctext x='50' y='64' font-size='48' text-anchor='middle' fill='white' font-family='sans-serif' font-weight='bold'%3EG%3C/text%3E%3C/svg%3E" />
  <link rel="manifest" href="data:application/manifest+json,%7B%22name%22%3A%22Gate%20Vehicle%20Register%22%2C%22short_name%22%3A%22Gate%20Register%22%2C%22display%22%3A%22standalone%22%2C%22background_color%22%3A%22%23f1f5f9%22%2C%22theme_color%22%3A%22%230f172a%22%7D" />
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet" />
  <style>
    body {
      font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
      background-color: #f1f5f9;
      -webkit-tap-highlight-color: transparent;
    }
    .bottom-tab-active {
      color: #ea580c;
    }
    .bottom-tab-active svg {
      stroke: #ea580c;
    }
    .no-scrollbar::-webkit-scrollbar { display: none; }
    .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
  </style>
</head>
<body class="min-h-screen text-slate-800 pb-24">

  <!-- Top Mobile App Header -->
  <header class="bg-slate-900 text-white sticky top-0 z-30 shadow-md">
    <div class="max-w-2xl mx-auto px-4 py-3 flex items-center justify-between gap-3">
      <div class="flex items-center gap-2.5 min-w-0">
        <div id="headerLogoWrap" class="w-10 h-10 rounded-xl bg-orange-600 flex items-center justify-center shrink-0 shadow overflow-hidden">
          <img id="headerLogoImg" src="" alt="Company Logo" class="hidden w-full h-full object-cover" />
          <svg id="headerLogoDefault" class="w-5 h-5 text-white" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M9 17a2 2 0 11-4 0 2 2 0 014 0zM19 17a2 2 0 11-4 0 2 2 0 014 0z" />
            <path stroke-linecap="round" stroke-linejoin="round" d="M13 16V6a1 1 0 00-1-1H4a1 1 0 00-1 1v10a1 1 0 001 1h1m8-1a1 1 0 01-1 1H9m4-1V8a1 1 0 011-1h2.586a1 1 0 01.707.293l3.414 3.414a1 1 0 01.293.707V16a1 1 0 01-1 1h-1m-6-1a1 1 0 001 1h1M5 17a2 2 0 104 0m-4 0a2 2 0 114 0m6 0a2 2 0 104 0m-4 0a2 2 0 114 0" />
          </svg>
        </div>
        <div class="min-w-0">
          <h1 id="headerCompanyName" class="text-sm sm:text-base font-bold truncate">Satvik Crunch Factory</h1>
          <p class="text-[11px] text-slate-300 truncate"><span id="headerCompanyAddress">Nimgaon Ketki, Indapur</span> • <span id="liveClock">--:--</span></p>
        </div>
      </div>
      <div class="flex items-center gap-2 shrink-0">
        <span id="insideBadgeTop" class="inline-flex items-center gap-1.5 px-2.5 py-1 rounded-full text-xs font-semibold bg-amber-500/20 text-amber-300 border border-amber-400/30">
          <span class="w-2 h-2 rounded-full bg-amber-400 animate-pulse"></span>
          <span id="insideCountTop">0</span> Inside
        </span>
        <button id="btnHeaderEditCompany" type="button" title="Edit Company Details" class="p-2 rounded-lg bg-slate-800 hover:bg-slate-700 text-slate-200 transition">
          <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" />
          </svg>
        </button>
      </div>
    </div>
  </header>

  <main class="max-w-2xl mx-auto px-3 sm:px-4 pt-4 space-y-4">

    <!-- TAB 1: NEW VEHICLE IN ENTRY -->
    <section id="view-entry" class="tab-view space-y-4">
      <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-4 sm:p-5">
        <div class="flex items-center justify-between mb-3">
          <div>
            <h2 class="text-base sm:text-lg font-bold text-slate-900">Vehicle Entry Form</h2>
            <p class="text-xs text-slate-500">Auto-records current date &amp; time on save</p>
          </div>
          <span id="formTimeBadge" class="px-2.5 py-1 rounded-lg bg-emerald-50 text-emerald-700 text-xs font-semibold border border-emerald-200">
            <span id="formTimeLabel">IN</span>: <span id="formAutoTime">--:--</span>
          </span>
        </div>

        <!-- Vehicle IN / OUT Mode Switch -->
        <div class="grid grid-cols-2 gap-2 p-1 bg-slate-100 rounded-xl mb-4">
          <button id="btnModeIn" type="button"
            class="py-2.5 px-3 rounded-lg text-xs sm:text-sm font-bold bg-emerald-600 text-white shadow transition">
            Vehicle IN
          </button>
          <button id="btnModeOut" type="button"
            class="py-2.5 px-3 rounded-lg text-xs sm:text-sm font-bold text-slate-600 hover:text-slate-900 transition">
            Vehicle OUT
          </button>
        </div>

        <form id="vehicleInForm" class="space-y-4">
          <div class="p-3 rounded-xl bg-slate-50 border border-slate-200 space-y-2">
            <div class="flex items-center justify-between">
              <label for="inSavedVehicleSelect" class="block text-xs font-semibold text-slate-700">Company Vehicle (Quick Select)</label>
              <button id="btnQuickAddVehicle" type="button" class="text-xs font-bold text-orange-600 hover:underline">+ Add Company Vehicle</button>
            </div>
            <select id="inSavedVehicleSelect"
              class="w-full px-3 py-2.5 rounded-xl border border-slate-300 text-base sm:text-sm bg-white focus:outline-none focus:ring-2 focus:ring-orange-500">
              <option value="">-- Outside Vehicle (Type Manually Below) --</option>
            </select>
          </div>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
            <div>
              <label for="inVehicleNo" class="block text-xs font-semibold text-slate-700 mb-1">Vehicle Number *</label>
              <input id="inVehicleNo" type="text" required placeholder="e.g. MH 42 AB 1234"
                class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm font-bold uppercase tracking-wide focus:outline-none focus:ring-2 focus:ring-orange-500 focus:border-orange-500" />
            </div>
            <div>
              <label for="inVehicleType" class="block text-xs font-semibold text-slate-700 mb-1">Vehicle Type *</label>
              <select id="inVehicleType" required
                class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm bg-white focus:outline-none focus:ring-2 focus:ring-orange-500">
                <option value="Tempo">Tempo</option>
                <option value="Truck">Truck</option>
                <option value="Pickup">Pickup / Bolero</option>
                <option value="Two-Wheeler">Two-Wheeler</option>
                <option value="Car">Car / SUV</option>
                <option value="Tractor">Tractor / Trolley</option>
                <option value="Other">Other</option>
              </select>
            </div>
          </div>

          <div class="p-3 rounded-xl bg-slate-50 border border-slate-200 space-y-2">
            <div class="flex items-center justify-between">
              <label for="inSavedDriverSelect" class="block text-xs font-semibold text-slate-700">Saved Driver (Quick Select)</label>
              <button id="btnQuickAddDriver" type="button" class="text-xs font-bold text-orange-600 hover:underline">+ Add Driver</button>
            </div>
            <select id="inSavedDriverSelect"
              class="w-full px-3 py-2.5 rounded-xl border border-slate-300 text-base sm:text-sm bg-white focus:outline-none focus:ring-2 focus:ring-orange-500">
              <option value="">-- Outside Driver (Type Manually Below) --</option>
            </select>
          </div>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
            <div>
              <label for="inDriverName" class="block text-xs font-semibold text-slate-700 mb-1">Driver Name *</label>
              <input id="inDriverName" type="text" required placeholder="Enter driver full name"
                class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
            </div>
            <div>
              <label for="inDriverMobile" class="block text-xs font-semibold text-slate-700 mb-1">Driver Mobile Number</label>
              <input id="inDriverMobile" type="tel" inputmode="numeric" maxlength="15" placeholder="10-digit mobile number"
                class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
            </div>
          </div>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
            <div>
              <label for="inPartyName" class="block text-xs font-semibold text-slate-700 mb-1">Party / Company Name *</label>
              <input id="inPartyName" type="text" required placeholder="e.g. Shree Balaji Oils / Visitor"
                class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
            </div>
            <div>
              <label for="inCategory" class="block text-xs font-semibold text-slate-700 mb-1">Purpose / Material Type *</label>
              <select id="inCategory" required
                class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm bg-white focus:outline-none focus:ring-2 focus:ring-orange-500">
                <option value="Raw Material">Raw Material (Inward)</option>
                <option value="Finished Goods">Finished Goods (Dispatch)</option>
                <option value="Packaging / Oil">Packaging / Edible Oil</option>
                <option value="Maintenance / Service">Maintenance / Service</option>
                <option value="Visitor / Guest">Visitor / Guest</option>
                <option value="Other">Other</option>
              </select>
            </div>
          </div>

          <div>
            <label for="inMaterialDetails" class="block text-xs font-semibold text-slate-700 mb-1">Material / Bill / Remark</label>
            <input id="inMaterialDetails" type="text" placeholder="e.g. Chipping Potatoes, 200 Tins Palm Oil, Invoice #412"
              class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
          </div>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
            <div>
              <label id="lblMaterialWeight" for="inMaterialWeight" class="block text-xs font-semibold text-slate-700 mb-1">Material Weight / Qty (Inward / Dispatch)</label>
              <div class="flex gap-1.5">
                <input id="inMaterialWeight" type="number" step="any" min="0" placeholder="e.g. 2500"
                  class="w-full px-3 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
                <select id="inWeightUnit" class="px-2.5 py-3 rounded-xl border border-slate-300 text-xs font-semibold bg-slate-50">
                  <option value="KG">KG</option>
                  <option value="TON">TON</option>
                  <option value="Bags">Bags</option>
                  <option value="Boxes">Boxes</option>
                </select>
              </div>
            </div>
            <div>
              <label id="lblEntryReading" for="inReadingVal" class="block text-xs font-semibold text-slate-700 mb-1">IN KM Reading</label>
              <div class="flex gap-1.5">
                <input id="inReadingVal" type="number" step="any" min="0" placeholder="Odometer KM"
                  class="w-full px-3 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
                <select id="inReadingUnit" class="px-2.5 py-3 rounded-xl border border-slate-300 text-xs font-semibold bg-slate-50">
                  <option value="KM">KM</option>
                  <option value="KG">KG</option>
                </select>
              </div>
            </div>
          </div>

          <div>
            <label class="block text-xs font-semibold text-slate-700 mb-1.5">Vehicle or Bill Photo (Optional)</label>
            <div class="flex items-center gap-3 flex-wrap">
              <label for="inPhotoInput"
                class="cursor-pointer inline-flex items-center gap-2 px-4 py-3 rounded-xl bg-slate-100 hover:bg-slate-200 text-slate-700 text-xs font-semibold border border-slate-300 transition">
                <svg class="w-4 h-4 text-orange-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M3 9a2 2 0 012-2h.93a2 2 0 001.664-.89l.812-1.22A2 2 0 0110.07 4h3.86a2 2 0 011.664.89l.812 1.22A2 2 0 0018.07 7H19a2 2 0 012 2v9a2 2 0 01-2 2H5a2 2 0 01-2-2V9z" />
                  <path stroke-linecap="round" stroke-linejoin="round" d="M15 13a3 3 0 11-6 0 3 3 0 016 0z" />
                </svg>
                Open Camera / Photo
              </label>
              <input id="inPhotoInput" type="file" accept="image/*" capture="environment" class="hidden" />
              <div id="inPhotoPreviewWrap" class="hidden items-center gap-2">
                <img id="inPhotoPreview" src="" alt="Vehicle preview" class="w-12 h-12 rounded-lg object-cover border border-slate-300" />
                <button id="btnClearInPhoto" type="button" class="text-xs text-red-600 font-semibold hover:underline">Remove</button>
              </div>
            </div>
          </div>

          <button type="submit"
            class="w-full py-3.5 px-4 rounded-xl bg-orange-600 hover:bg-orange-700 active:bg-orange-800 text-white font-bold text-sm shadow-md transition flex items-center justify-center gap-2">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" d="M11 16l-4-4m0 0l4-4m-4 4h14m-5 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h7a3 3 0 013 3v1" />
            </svg>
            <span id="btnSubmitEntryText">Save Vehicle IN Entry</span>
          </button>
        </form>
      </div>
    </section>

    <!-- TAB 2: VEHICLES CURRENTLY INSIDE -->
    <section id="view-inside" class="tab-view hidden space-y-3">
      <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-3 flex items-center gap-2">
        <svg class="w-4 h-4 text-slate-400 shrink-0 ml-1" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
        </svg>
        <input id="insideSearch" type="text" placeholder="Search vehicle no, party, or driver..."
          class="w-full text-base sm:text-sm focus:outline-none bg-transparent" />
      </div>
      <div id="insideList" class="space-y-3"></div>
    </section>

    <!-- TAB 3: ALL LOGS & HISTORY -->
    <section id="view-logs" class="tab-view hidden space-y-3">
      <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-3 space-y-2.5">
        <div class="flex items-center gap-2 border-b border-slate-100 pb-2">
          <svg class="w-4 h-4 text-slate-400 shrink-0" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
          </svg>
          <input id="logsSearch" type="text" placeholder="Search vehicle, party, driver, material..."
            class="w-full text-base sm:text-sm focus:outline-none bg-transparent" />
        </div>
        <div class="grid grid-cols-3 gap-2">
          <select id="filterDate" class="px-2.5 py-2.5 rounded-xl border border-slate-200 text-xs font-medium bg-slate-50">
            <option value="today">Today</option>
            <option value="yesterday">Yesterday</option>
            <option value="7days">Last 7 Days</option>
            <option value="all">All Dates</option>
          </select>
          <select id="filterStatus" class="px-2.5 py-2.5 rounded-xl border border-slate-200 text-xs font-medium bg-slate-50">
            <option value="all">All Status</option>
            <option value="IN">Inside Only</option>
            <option value="OUT">Exited Only</option>
          </select>
          <select id="filterCategory" class="px-2.5 py-2.5 rounded-xl border border-slate-200 text-xs font-medium bg-slate-50">
            <option value="all">All Purpose</option>
            <option value="Raw Material">Raw Material</option>
            <option value="Finished Goods">Finished Goods</option>
            <option value="Packaging / Oil">Packaging / Oil</option>
            <option value="Maintenance / Service">Maintenance</option>
            <option value="Visitor / Guest">Visitor</option>
            <option value="Other">Other</option>
          </select>
        </div>
      </div>

      <div id="logsList" class="space-y-3"></div>
    </section>

    <!-- TAB 4: DAILY WHATSAPP REPORT & EXPORT -->
    <section id="view-report" class="tab-view hidden space-y-4">
      <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-4 space-y-4">
        <div class="flex flex-wrap items-center justify-between gap-2">
          <div>
            <h2 class="text-base font-bold text-slate-900">Daily Gate Report</h2>
            <p class="text-xs text-slate-500">Share directly on WhatsApp or export to Excel</p>
          </div>
          <input id="reportDate" type="date"
            class="px-3 py-2 rounded-xl border border-slate-300 text-xs font-semibold bg-slate-50 focus:outline-none focus:ring-2 focus:ring-orange-500" />
        </div>

        <div class="grid grid-cols-2 sm:grid-cols-4 gap-2.5 text-center">
          <div class="p-3 rounded-xl bg-slate-50 border border-slate-200">
            <div id="repTotalIn" class="text-xl font-extrabold text-slate-900">0</div>
            <div class="text-[11px] font-medium text-slate-500">Total Entries</div>
          </div>
          <div class="p-3 rounded-xl bg-amber-50 border border-amber-200">
            <div id="repStillIn" class="text-xl font-extrabold text-amber-700">0</div>
            <div class="text-[11px] font-medium text-amber-700">Inside Now</div>
          </div>
          <div class="p-3 rounded-xl bg-emerald-50 border border-emerald-200">
            <div id="repExited" class="text-xl font-extrabold text-emerald-700">0</div>
            <div class="text-[11px] font-medium text-emerald-700">Outside / Exited</div>
          </div>
          <div class="p-3 rounded-xl bg-blue-50 border border-blue-200">
            <div id="repRawKg" class="text-xl font-extrabold text-blue-700">0 KG</div>
            <div class="text-[11px] font-medium text-blue-700">Raw Material Inward</div>
          </div>
        </div>

        <div>
          <label for="whatsappPreview" class="block text-xs font-semibold text-slate-700 mb-1.5">WhatsApp Message Preview</label>
          <textarea id="whatsappPreview" rows="10" readonly
            class="w-full p-3 rounded-xl border border-slate-300 bg-slate-50 text-xs font-mono leading-relaxed text-slate-800 focus:outline-none"></textarea>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 gap-2.5">
          <button id="btnShareWhatsApp" type="button"
            class="py-3.5 px-4 rounded-xl bg-green-600 hover:bg-green-700 text-white font-bold text-xs sm:text-sm shadow transition flex items-center justify-center gap-2">
            <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12.031 2c-5.516 0-9.969 4.453-9.969 9.969 0 1.766.469 3.484 1.344 5l-1.406 5.156 5.281-1.375c1.469.797 3.109 1.219 4.75 1.219 5.516 0 9.969-4.453 9.969-9.969s-4.453-10-9.969-10zm5.813 14.125c-.25.703-1.438 1.344-2 1.422-.516.078-1.188.109-1.922-.125-.453-.141-1.031-.344-1.766-.656-3.094-1.344-5.109-4.484-5.266-4.688-.156-.203-1.266-1.688-1.266-3.219s.797-2.281 1.078-2.594c.281-.313.609-.391.813-.391s.406.016.578.016c.188 0 .438-.078.688.516.25.609.859 2.094.938 2.25.078.156.125.344.016.547-.109.203-.156.344-.313.516-.156.172-.328.391-.469.531-.156.156-.313.328-.141.625.172.297.781 1.281 1.672 2.078 1.156 1.031 2.125 1.344 2.422 1.5.297.156.469.125.641-.078.172-.203.75-.875.953-1.172.203-.297.391-.25.656-.156.266.094 1.703.813 1.984.953.281.141.469.219.531.344.063.125.063.719-.188 1.422z"/>
            </svg>
            Share on WhatsApp
          </button>
          <button id="btnCopyReport" type="button"
            class="py-3.5 px-4 rounded-xl bg-slate-800 hover:bg-slate-900 text-white font-bold text-xs sm:text-sm shadow transition flex items-center justify-center gap-2">
            <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" d="M8 16H6a2 2 0 01-2-2V6a2 2 0 012-2h8a2 2 0 012 2v2m-6 12h8a2 2 0 002-2v-8a2 2 0 00-2-2h-8a2 2 0 00-2 2v8a2 2 0 002 2z" />
            </svg>
            Copy Report
          </button>
          <button id="btnExportCsv" type="button"
            class="py-3.5 px-4 rounded-xl bg-blue-600 hover:bg-blue-700 text-white font-bold text-xs sm:text-sm shadow transition flex items-center justify-center gap-2">
            <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4" />
            </svg>
            Export Excel (CSV)
          </button>
          <button id="btnEmailReport" type="button"
            class="py-3.5 px-4 rounded-xl bg-indigo-600 hover:bg-indigo-700 text-white font-bold text-xs sm:text-sm shadow transition flex items-center justify-center gap-2">
            <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
            </svg>
            Send Backup to Email
          </button>
        </div>
      </div>
    </section>

    <!-- TAB 5: COMPANY DETAILS & MOBILE SETTINGS -->
    <section id="view-company" class="tab-view hidden space-y-4">
      <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-4 sm:p-5 space-y-4">
        <div>
          <h2 class="text-base sm:text-lg font-bold text-slate-900">Company &amp; Gate Settings</h2>
          <p class="text-xs text-slate-500">Edit your company details shown in the header and WhatsApp reports</p>
        </div>

        <form id="companySettingsForm" class="space-y-3.5">
          <div>
            <label for="setCompanyName" class="block text-xs font-semibold text-slate-700 mb-1">Company / Factory Name *</label>
            <input id="setCompanyName" type="text" required placeholder="e.g. Satvik Crunch Factory"
              class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
          </div>
          <div>
            <label for="setCompanyAddress" class="block text-xs font-semibold text-slate-700 mb-1">Factory Address / Location</label>
            <input id="setCompanyAddress" type="text" placeholder="e.g. Nimgaon Ketki, Indapur, Pune"
              class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
          </div>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
            <div>
              <label for="setCompanyPhone" class="block text-xs font-semibold text-slate-700 mb-1">Company Phone Number</label>
              <input id="setCompanyPhone" type="tel" placeholder="e.g. 9876543210"
                class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
            </div>
            <div>
              <label for="setCompanyGstin" class="block text-xs font-semibold text-slate-700 mb-1">GSTIN / Gate Name (Optional)</label>
              <input id="setCompanyGstin" type="text" placeholder="e.g. Main Gate 1"
                class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
            </div>
          </div>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
            <div>
              <label for="setGuardName" class="block text-xs font-semibold text-slate-700 mb-1">Security Guard / Shift Name</label>
              <input id="setGuardName" type="text" placeholder="e.g. Main Gate Security"
                class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
            </div>
            <div>
              <label for="setOwnerWhatsapp" class="block text-xs font-semibold text-slate-700 mb-1">Owner WhatsApp No (with 91)</label>
              <input id="setOwnerWhatsapp" type="tel" inputmode="numeric" placeholder="e.g. 919876543210"
                class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
            </div>
          </div>

          <div>
            <label for="setBackupEmail" class="block text-xs font-semibold text-slate-700 mb-1">Backup Email Address (Gmail / Email)</label>
            <input id="setBackupEmail" type="email" placeholder="e.g. satvikcrunch@gmail.com"
              class="w-full px-3.5 py-3 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
          </div>

          <label class="flex items-center gap-2.5 p-3 rounded-xl bg-green-50 border border-green-200 cursor-pointer">
            <input id="setAutoPromptWa" type="checkbox" checked class="w-4 h-4 accent-green-600 rounded" />
            <span class="text-xs font-semibold text-green-900">Auto-open WhatsApp Group share after every IN / OUT entry</span>
          </label>

          <div>
            <label class="block text-xs font-semibold text-slate-700 mb-1.5">Company Logo (Optional)</label>
            <div class="flex items-center gap-3 flex-wrap">
              <label for="setLogoInput"
                class="cursor-pointer inline-flex items-center gap-2 px-4 py-2.5 rounded-xl bg-slate-100 hover:bg-slate-200 text-slate-700 text-xs font-semibold border border-slate-300">
                Upload Logo
              </label>
              <input id="setLogoInput" type="file" accept="image/*" class="hidden" />
              <div id="setLogoPreviewWrap" class="hidden items-center gap-2">
                <img id="setLogoPreview" src="" alt="Logo preview" class="w-10 h-10 rounded-lg object-cover border border-slate-300" />
                <button id="btnClearLogo" type="button" class="text-xs text-red-600 font-semibold hover:underline">Remove</button>
              </div>
            </div>
          </div>

          <button type="submit"
            class="w-full py-3.5 rounded-xl bg-orange-600 hover:bg-orange-700 text-white text-sm font-bold shadow">
            Save Company Details
          </button>
        </form>

        <!-- Company Vehicles List Manager -->
        <div class="pt-4 border-t border-slate-200 space-y-3">
          <div>
            <h3 class="text-sm font-bold text-slate-900">Company Vehicles List</h3>
            <p class="text-[11px] text-slate-500">Add your company vehicles here to select them quickly from the dropdown</p>
          </div>
          <div class="flex gap-2 flex-wrap sm:flex-nowrap">
            <input id="newCompVehNo" type="text" placeholder="Vehicle No (e.g. MH 42 AQ 8412)"
              class="flex-1 min-w-[150px] px-3 py-2.5 rounded-xl border border-slate-300 text-sm font-bold uppercase" />
            <select id="newCompVehType" class="px-3 py-2.5 rounded-xl border border-slate-300 text-sm bg-white">
              <option value="Tempo">Tempo</option>
              <option value="Truck">Truck</option>
              <option value="Pickup">Pickup / Bolero</option>
              <option value="Two-Wheeler">Two-Wheeler</option>
              <option value="Car">Car / SUV</option>
              <option value="Tractor">Tractor</option>
              <option value="Other">Other</option>
            </select>
            <button id="btnAddCompVehicle" type="button" class="px-4 py-2.5 rounded-xl bg-slate-900 hover:bg-slate-800 text-white text-xs font-bold shrink-0">
              + Add
            </button>
          </div>
          <div id="compVehiclesList" class="space-y-1.5"></div>
        </div>

        <!-- Company Drivers List Manager -->
        <div class="pt-4 border-t border-slate-200 space-y-3">
          <div>
            <h3 class="text-sm font-bold text-slate-900">Saved Drivers List</h3>
            <p class="text-[11px] text-slate-500">Add your regular drivers here to select them quickly from the dropdown</p>
          </div>
          <div class="flex gap-2 flex-wrap sm:flex-nowrap">
            <input id="newCompDriverName" type="text" placeholder="Driver Name"
              class="flex-1 min-w-[140px] px-3 py-2.5 rounded-xl border border-slate-300 text-sm" />
            <input id="newCompDriverMobile" type="tel" inputmode="numeric" maxlength="15" placeholder="Mobile Number"
              class="flex-1 min-w-[130px] px-3 py-2.5 rounded-xl border border-slate-300 text-sm" />
            <button id="btnAddCompDriver" type="button" class="px-4 py-2.5 rounded-xl bg-slate-900 hover:bg-slate-800 text-white text-xs font-bold shrink-0">
              + Add
            </button>
          </div>
          <div id="compDriversList" class="space-y-1.5"></div>
        </div>

        <div class="pt-4 border-t border-slate-200 space-y-2">
          <div class="p-3.5 rounded-xl bg-indigo-50 border border-indigo-200 space-y-2.5">
            <div>
              <h3 class="text-xs font-bold text-indigo-950">Email &amp; File Backup (Never Lose Data)</h3>
              <p class="text-[11px] text-indigo-800">Save your backup email above, then send daily backups or download a full backup file.</p>
            </div>
            <div class="grid grid-cols-1 sm:grid-cols-3 gap-2">
              <button id="btnCompanyEmailBackup" type="button" class="py-2.5 px-3 rounded-xl bg-indigo-600 hover:bg-indigo-700 text-white text-xs font-bold shadow">
                Email All Data
              </button>
              <button id="btnDownloadJson" type="button" class="py-2.5 px-3 rounded-xl bg-slate-800 hover:bg-slate-900 text-white text-xs font-bold shadow">
                Download Backup
              </button>
              <label for="restoreJsonInput" class="cursor-pointer py-2.5 px-3 rounded-xl bg-white hover:bg-slate-50 text-slate-800 border border-slate-300 text-xs font-bold text-center">
                Restore Backup
              </label>
              <input id="restoreJsonInput" type="file" accept=".json,application/json" class="hidden" />
            </div>
          </div>

          <div class="p-3.5 rounded-xl bg-blue-50 border border-blue-200 text-xs text-blue-900 space-y-1">
            <p class="font-bold">How to Open as a Mobile App on Phone Screen (No Computer):</p>
            <p>1. Download this <strong>.html</strong> file on your phone.</p>
            <p>2. Open <strong>app.netlify.com/drop</strong> (or <strong>tiiny.host</strong>) in Chrome on your phone and upload this file to get a free <strong>https://</strong> link.</p>
            <p>3. Open that link in Chrome &rarr; tap <strong>&vellip; &rarr; Install app / Add to Home screen</strong>. It will open full-screen like a real Android app!</p>
          </div>
          <div class="flex items-center justify-between pt-2">
            <button id="btnLoadSampleData" type="button" class="text-xs font-semibold text-blue-600 hover:underline">Load Demo Entries</button>
            <button id="btnClearAllData" type="button" class="text-xs font-semibold text-red-600 hover:underline">Clear All Gate Data</button>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- MOBILE BOTTOM NAVIGATION BAR -->
  <nav class="fixed bottom-0 inset-x-0 bg-white border-t border-slate-200 z-30 shadow-lg">
    <div class="max-w-2xl mx-auto grid grid-cols-5 text-[11px] font-semibold text-slate-500">
      <button type="button" data-tab="entry" class="nav-tab bottom-tab-active py-2 px-1 flex flex-col items-center gap-0.5">
        <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M12 4v16m8-8H4" />
        </svg>
        <span>Entry</span>
      </button>
      <button type="button" data-tab="inside" class="nav-tab py-2 px-1 flex flex-col items-center gap-0.5 relative">
        <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M9 17a2 2 0 11-4 0 2 2 0 014 0zM19 17a2 2 0 11-4 0 2 2 0 014 0z" />
          <path stroke-linecap="round" stroke-linejoin="round" d="M13 16V6a1 1 0 00-1-1H4a1 1 0 00-1 1v10a1 1 0 001 1h1m8-1a1 1 0 01-1 1H9m4-1V8a1 1 0 011-1h2.586a1 1 0 01.707.293l3.414 3.414a1 1 0 01.293.707V16a1 1 0 01-1 1h-1" />
        </svg>
        <span>Inside (<span id="insideCountTab">0</span>)</span>
      </button>
      <button type="button" data-tab="logs" class="nav-tab py-2 px-1 flex flex-col items-center gap-0.5">
        <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2" />
        </svg>
        <span>Logs</span>
      </button>
      <button type="button" data-tab="report" class="nav-tab py-2 px-1 flex flex-col items-center gap-0.5">
        <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M8.684 13.342C8.886 12.938 9 12.482 9 12c0-.482-.114-.938-.316-1.342m0 2.684a3 3 0 110-2.684m0 2.684l6.632 3.316m-6.632-6l6.632-3.316m0 0a3 3 0 105.367-2.684 3 3 0 00-5.367 2.684zm0 9.316a3 3 0 105.368 2.684 3 3 0 00-5.368-2.684z" />
        </svg>
        <span>Report</span>
      </button>
      <button type="button" data-tab="company" class="nav-tab py-2 px-1 flex flex-col items-center gap-0.5">
        <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4" />
        </svg>
        <span>Company</span>
      </button>
    </div>
  </nav>

  <!-- MARK OUT MODAL -->
  <div id="checkoutModal" class="fixed inset-0 bg-slate-900/60 z-50 hidden items-center justify-center p-4">
    <div class="bg-white rounded-2xl max-w-md w-full p-5 shadow-xl space-y-4">
      <div class="flex items-start justify-between">
        <div>
          <h3 class="text-base font-bold text-slate-900">Mark Vehicle OUT</h3>
          <p id="outVehicleSummary" class="text-xs text-slate-500 mt-0.5"></p>
        </div>
        <button id="btnCloseCheckout" type="button" class="text-slate-400 hover:text-slate-600 text-lg font-bold px-2">&times;</button>
      </div>
      <form id="checkoutForm" class="space-y-3">
        <input id="outEntryId" type="hidden" />
        <div>
          <label for="outReadingVal" class="block text-xs font-semibold text-slate-700 mb-1">
            OUT Reading (<span id="outReadingUnitLabel">KM</span>) — Optional
          </label>
          <input id="outReadingVal" type="number" step="any" min="0" placeholder="Enter OUT KM or Weight"
            class="w-full px-3.5 py-2.5 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
        </div>
        <div>
          <label for="outRemark" class="block text-xs font-semibold text-slate-700 mb-1">OUT Remark / Gate Pass Note</label>
          <input id="outRemark" type="text" placeholder="e.g. Empty / Loaded Dispatch #104"
            class="w-full px-3.5 py-2.5 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-orange-500" />
        </div>
        <div>
          <label class="block text-xs font-semibold text-slate-700 mb-1">OUT Photo (Optional)</label>
          <div class="flex items-center gap-3">
            <label for="outPhotoInput" class="cursor-pointer px-3 py-2 rounded-xl bg-slate-100 hover:bg-slate-200 text-xs font-semibold border border-slate-300">
              Capture Photo
            </label>
            <input id="outPhotoInput" type="file" accept="image/*" capture="environment" class="hidden" />
            <img id="outPhotoPreview" src="" alt="Out preview" class="hidden w-10 h-10 rounded-lg object-cover border border-slate-300" />
          </div>
        </div>
        <div class="flex gap-2 pt-2">
          <button id="btnCancelCheckout" type="button" class="flex-1 py-2.5 rounded-xl border border-slate-300 text-xs font-semibold text-slate-700 hover:bg-slate-50">Cancel</button>
          <button type="submit" class="flex-1 py-2.5 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white text-xs font-bold shadow">Confirm Vehicle OUT</button>
        </div>
      </form>
    </div>
  </div>

  <!-- MARK RETURN IN MODAL -->
  <div id="returnInModal" class="fixed inset-0 bg-slate-900/60 z-50 hidden items-center justify-center p-4">
    <div class="bg-white rounded-2xl max-w-md w-full p-5 shadow-xl space-y-4">
      <div class="flex items-start justify-between">
        <div>
          <h3 class="text-base font-bold text-slate-900">Mark Vehicle Return IN</h3>
          <p id="retVehicleSummary" class="text-xs text-slate-500 mt-0.5"></p>
        </div>
        <button id="btnCloseReturn" type="button" class="text-slate-400 hover:text-slate-600 text-lg font-bold px-2">&times;</button>
      </div>
      <form id="returnInForm" class="space-y-3 max-h-[75vh] overflow-y-auto pr-0.5">
        <input id="retEntryId" type="hidden" />

        <!-- Empty vs With Material Toggle -->
        <div>
          <span class="block text-xs font-semibold text-slate-700 mb-1.5">Return Status *</span>
          <div class="grid grid-cols-2 gap-2 p-1 bg-slate-100 rounded-xl">
            <button id="btnRetEmpty" type="button" class="py-2 px-2 rounded-lg text-xs font-bold bg-blue-600 text-white shadow transition">
              Empty Return
            </button>
            <button id="btnRetWithMat" type="button" class="py-2 px-2 rounded-lg text-xs font-bold text-slate-600 hover:text-slate-900 transition">
              With Material
            </button>
          </div>
        </div>

        <!-- Collapsible Return Material Fields (Shown only when With Material is selected) -->
        <div id="retMaterialSection" class="hidden space-y-2.5 p-3 rounded-xl bg-blue-50 border border-blue-200">
          <div>
            <label for="retFromParty" class="block text-xs font-semibold text-blue-900 mb-1">Material From (Supplier / Party Name)</label>
            <input id="retFromParty" type="text" placeholder="e.g. Kisan Agro Farms (where material was picked up)"
              class="w-full px-3 py-2 rounded-xl border border-blue-200 text-sm bg-white" />
          </div>
          <div>
            <label for="retMatType" class="block text-xs font-semibold text-blue-900 mb-1">Material Category</label>
            <select id="retMatType" class="w-full px-3 py-2 rounded-xl border border-blue-200 text-sm bg-white">
              <option value="Raw Material">Raw Material (Inward)</option>
              <option value="Packaging / Oil">Packaging / Edible Oil</option>
              <option value="Sales Return">Sales Return / Goods</option>
              <option value="Other">Other Material</option>
            </select>
          </div>
          <div>
            <label for="retMatDetails" class="block text-xs font-semibold text-blue-900 mb-1">Material Name / Details</label>
            <input id="retMatDetails" type="text" placeholder="e.g. 50 Bags Potatoes / Empty Crates"
              class="w-full px-3 py-2 rounded-xl border border-blue-200 text-sm bg-white" />
          </div>
          <div>
            <label for="retMatWeight" class="block text-xs font-semibold text-blue-900 mb-1">Quantity / Weight</label>
            <div class="flex gap-1.5">
              <input id="retMatWeight" type="number" step="any" min="0" placeholder="e.g. 1200"
                class="w-full px-3 py-2 rounded-xl border border-blue-200 text-sm bg-white" />
              <select id="retMatUnit" class="px-2.5 py-2 rounded-xl border border-blue-200 text-xs font-semibold bg-white">
                <option value="KG">KG</option>
                <option value="TON">TON</option>
                <option value="Bags">Bags</option>
                <option value="Boxes">Boxes</option>
              </select>
            </div>
          </div>
        </div>

        <div>
          <label for="retReadingVal" class="block text-xs font-semibold text-slate-700 mb-1">
            Return IN Reading (<span id="retReadingUnitLabel">KM</span>) — Optional
          </label>
          <input id="retReadingVal" type="number" step="any" min="0" placeholder="Enter Return IN KM"
            class="w-full px-3.5 py-2.5 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-blue-500" />
        </div>
        <div>
          <label for="retRemark" class="block text-xs font-semibold text-slate-700 mb-1">Return IN Note (Optional)</label>
          <input id="retRemark" type="text" placeholder="e.g. Empty returned from party"
            class="w-full px-3.5 py-2.5 rounded-xl border border-slate-300 text-base sm:text-sm focus:outline-none focus:ring-2 focus:ring-blue-500" />
        </div>
        <div>
          <label class="block text-xs font-semibold text-slate-700 mb-1">Return IN Vehicle Photo (Optional)</label>
          <div class="flex items-center gap-3">
            <label for="retPhotoInput" class="cursor-pointer px-3.5 py-2.5 rounded-xl bg-slate-100 hover:bg-slate-200 text-xs font-semibold border border-slate-300">
              Capture / Upload Photo
            </label>
            <input id="retPhotoInput" type="file" accept="image/*" capture="environment" class="hidden" />
            <img id="retPhotoPreview" src="" alt="Return IN preview" class="hidden w-12 h-12 rounded-lg object-cover border border-slate-300" />
          </div>
        </div>
        <div class="flex gap-2 pt-2">
          <button id="btnCancelReturn" type="button" class="flex-1 py-2.5 rounded-xl border border-slate-300 text-xs font-semibold text-slate-700 hover:bg-slate-50">Cancel</button>
          <button type="submit" class="flex-1 py-2.5 rounded-xl bg-blue-600 hover:bg-blue-700 text-white text-xs font-bold shadow">Confirm Return IN</button>
        </div>
      </form>
    </div>
  </div>

  <!-- EDIT ENTRY MODAL -->
  <div id="editModal" class="fixed inset-0 bg-slate-900/60 z-50 hidden items-center justify-center p-4">
    <div class="bg-white rounded-2xl max-w-md w-full p-5 shadow-xl space-y-3 max-h-[90vh] overflow-y-auto">
      <div class="flex items-center justify-between">
        <h3 class="text-base font-bold text-slate-900">Edit Vehicle Entry</h3>
        <button id="btnCloseEdit" type="button" class="text-slate-400 hover:text-slate-600 text-lg font-bold px-2">&times;</button>
      </div>
      <form id="editForm" class="space-y-3">
        <input id="editEntryId" type="hidden" />
        <div class="grid grid-cols-2 gap-2">
          <div>
            <label for="editVehicleNo" class="block text-xs font-semibold text-slate-700 mb-1">Vehicle No *</label>
            <input id="editVehicleNo" type="text" required class="w-full px-3 py-2 rounded-xl border border-slate-300 text-sm font-bold uppercase" />
          </div>
          <div>
            <label for="editVehicleType" class="block text-xs font-semibold text-slate-700 mb-1">Type</label>
            <select id="editVehicleType" class="w-full px-3 py-2 rounded-xl border border-slate-300 text-sm bg-white">
              <option value="Tempo">Tempo</option>
              <option value="Truck">Truck</option>
              <option value="Pickup">Pickup / Bolero</option>
              <option value="Two-Wheeler">Two-Wheeler</option>
              <option value="Car">Car / SUV</option>
              <option value="Tractor">Tractor / Trolley</option>
              <option value="Other">Other</option>
            </select>
          </div>
        </div>
        <div class="grid grid-cols-2 gap-2">
          <div>
            <label for="editDriverName" class="block text-xs font-semibold text-slate-700 mb-1">Driver Name *</label>
            <input id="editDriverName" type="text" required class="w-full px-3 py-2 rounded-xl border border-slate-300 text-sm" />
          </div>
          <div>
            <label for="editDriverMobile" class="block text-xs font-semibold text-slate-700 mb-1">Mobile</label>
            <input id="editDriverMobile" type="tel" class="w-full px-3 py-2 rounded-xl border border-slate-300 text-sm" />
          </div>
        </div>
        <div>
          <label for="editPartyName" class="block text-xs font-semibold text-slate-700 mb-1">Party / Company Name *</label>
          <input id="editPartyName" type="text" required class="w-full px-3 py-2 rounded-xl border border-slate-300 text-sm" />
        </div>
        <div>
          <label for="editMaterialDetails" class="block text-xs font-semibold text-slate-700 mb-1">Material / Details</label>
          <input id="editMaterialDetails" type="text" class="w-full px-3 py-2 rounded-xl border border-slate-300 text-sm" />
        </div>
        <div class="grid grid-cols-2 gap-2">
          <div>
            <label for="editInReading" class="block text-xs font-semibold text-slate-700 mb-1">IN Reading</label>
            <input id="editInReading" type="number" step="any" class="w-full px-3 py-2 rounded-xl border border-slate-300 text-sm" />
          </div>
          <div>
            <label for="editOutReading" class="block text-xs font-semibold text-slate-700 mb-1">OUT Reading</label>
            <input id="editOutReading" type="number" step="any" class="w-full px-3 py-2 rounded-xl border border-slate-300 text-sm" />
          </div>
        </div>
        <div class="flex gap-2 pt-2">
          <button id="btnCancelEdit" type="button" class="flex-1 py-2.5 rounded-xl border border-slate-300 text-xs font-semibold text-slate-700">Cancel</button>
          <button type="submit" class="flex-1 py-2.5 rounded-xl bg-orange-600 hover:bg-orange-700 text-white text-xs font-bold">Save Changes</button>
        </div>
      </form>
    </div>
  </div>

  <!-- PHOTO VIEWER MODAL -->
  <div id="photoModal" class="fixed inset-0 bg-slate-900/80 z-50 hidden items-center justify-center p-4">
    <div class="bg-white rounded-2xl max-w-lg w-full p-3 shadow-2xl space-y-2">
      <div class="flex items-center justify-between px-1">
        <span id="photoModalTitle" class="text-xs font-bold text-slate-700">Photo</span>
        <button id="btnClosePhoto" type="button" class="text-slate-500 hover:text-slate-800 text-lg font-bold px-2">&times;</button>
      </div>
      <img id="photoModalImg" src="" alt="Full vehicle photo" class="w-full max-h-[75vh] object-contain rounded-xl bg-slate-100" />
    </div>
  </div>

  <!-- CONFIRM DELETE MODAL -->
  <div id="confirmModal" class="fixed inset-0 bg-slate-900/60 z-50 hidden items-center justify-center p-4">
    <div class="bg-white rounded-2xl max-w-sm w-full p-5 shadow-xl space-y-4">
      <h3 id="confirmTitle" class="text-sm font-bold text-slate-900">Confirm Action</h3>
      <p id="confirmMessage" class="text-xs text-slate-600"></p>
      <div class="flex gap-2">
        <button id="btnConfirmCancel" type="button" class="flex-1 py-2 rounded-xl border border-slate-300 text-xs font-semibold text-slate-700">Cancel</button>
        <button id="btnConfirmOk" type="button" class="flex-1 py-2 rounded-xl bg-red-600 hover:bg-red-700 text-white text-xs font-bold">Confirm</button>
      </div>
    </div>
  </div>

  <!-- SINGLE ENTRY WHATSAPP SHARE MODAL -->
  <div id="waSingleModal" class="fixed inset-0 bg-slate-900/60 z-50 hidden items-center justify-center p-4">
    <div class="bg-white rounded-2xl max-w-md w-full p-5 shadow-xl space-y-3">
      <div class="flex items-center justify-between">
        <div>
          <h3 id="waSingleTitle" class="text-base font-bold text-slate-900">Send Entry to WhatsApp Group</h3>
          <p class="text-[11px] text-slate-500">Tap Send, then select your factory WhatsApp group</p>
        </div>
        <button id="btnWaSingleCloseX" type="button" class="text-slate-400 hover:text-slate-600 text-lg font-bold px-2">&times;</button>
      </div>
      <div id="waSinglePhotoRow" class="hidden items-center gap-2.5 p-2 rounded-xl bg-slate-50 border border-slate-200">
        <img id="waSinglePhotoThumb" src="" alt="Attached photo" class="w-11 h-11 rounded-lg object-cover border border-slate-300 shrink-0" />
        <div class="text-xs text-slate-700">
          <p class="font-bold text-emerald-700">Vehicle / Bill Photo Attached</p>
          <p class="text-[11px] text-slate-500">Will be sent with report details as caption</p>
        </div>
      </div>
      <textarea id="waSingleText" rows="7" readonly
        class="w-full p-3 rounded-xl border border-slate-300 bg-slate-50 text-xs font-mono leading-relaxed text-slate-800 focus:outline-none"></textarea>
      <div class="flex gap-2">
        <button id="btnWaSingleSend" type="button"
          class="flex-1 py-3 px-3 rounded-xl bg-green-600 hover:bg-green-700 text-white text-xs font-bold shadow flex items-center justify-center gap-1.5">
          <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12.031 2c-5.516 0-9.969 4.453-9.969 9.969 0 1.766.469 3.484 1.344 5l-1.406 5.156 5.281-1.375c1.469.797 3.109 1.219 4.75 1.219 5.516 0 9.969-4.453 9.969-9.969s-4.453-10-9.969-10zm5.813 14.125c-.25.703-1.438 1.344-2 1.422-.516.078-1.188.109-1.922-.125-.453-.141-1.031-.344-1.766-.656-3.094-1.344-5.109-4.484-5.266-4.688-.156-.203-1.266-1.688-1.266-3.219s.797-2.281 1.078-2.594c.281-.313.609-.391.813-.391s.406.016.578.016c.188 0 .438-.078.688.516.25.609.859 2.094.938 2.25.078.156.125.344.016.547-.109.203-.156.344-.313.516-.156.172-.328.391-.469.531-.156.156-.313.328-.141.625.172.297.781 1.281 1.672 2.078 1.156 1.031 2.125 1.344 2.422 1.5.297.156.469.125.641-.078.172-.203.75-.875.953-1.172.203-.297.391-.25.656-.156.266.094 1.703.813 1.984.953.281.141.469.219.531.344.063.125.063.719-.188 1.422z"/>
          </svg>
          Send to WhatsApp Group
        </button>
        <button id="btnWaSingleCopy" type="button"
          class="px-3.5 py-3 rounded-xl bg-slate-800 hover:bg-slate-900 text-white text-xs font-bold">
          Copy
        </button>
        <button id="btnWaSingleClose" type="button"
          class="px-3.5 py-3 rounded-xl border border-slate-300 text-slate-700 text-xs font-semibold">
          Done
        </button>
      </div>
    </div>
  </div>

  <!-- TOAST -->
  <div id="toast" class="fixed bottom-20 left-1/2 -translate-x-1/2 z-50 hidden px-4 py-2.5 rounded-xl bg-slate-900 text-white text-xs font-semibold shadow-lg"></div>

  <script>
    (function () {
      const STORAGE_KEY = 'satvik_gate_entries_v1';
      const SETTINGS_KEY = 'satvik_gate_settings_v1';

      let entries = [];
      let settings = {
        companyName: 'Satvik Crunch Factory',
        companyAddress: 'Nimgaon Ketki, Indapur, Pune',
        companyPhone: '',
        companyGstin: 'Main Gate',
        guardName: 'Main Gate Security',
        ownerWhatsapp: '',
        backupEmail: '',
        companyLogo: '',
        autoPromptWa: true,
        companyVehicles: [],
        companyDrivers: []
      };
      let inPhotoBase64 = '';
      let outPhotoBase64 = '';
      let retPhotoBase64 = '';
      let pendingLogoBase64 = '';
      let entryMode = 'IN';
      let returnMode = 'EMPTY';
      let confirmCallback = null;

      function safeGetStorage(key) {
        try { return localStorage.getItem(key); } catch (e) { return null; }
      }
      function safeSetStorage(key, val) {
        try { localStorage.setItem(key, val); } catch (e) { showToast('Storage limit reached. Remove old photos if needed.'); }
      }

      function toLocalDateISO(dateInput) {
        if (!dateInput) return '';
        const d = new Date(dateInput);
        if (isNaN(d.getTime())) return '';
        const y = d.getFullYear();
        const m = String(d.getMonth() + 1).padStart(2, '0');
        const day = String(d.getDate()).padStart(2, '0');
        return `${y}-${m}-${day}`;
      }

      function todayISO() {
        return toLocalDateISO(new Date());
      }

      function formatTime(isoStr) {
        if (!isoStr) return '--:--';
        const d = new Date(isoStr);
        return d.toLocaleTimeString('en-IN', { hour: '2-digit', minute: '2-digit', hour12: true });
      }

      function formatDate(isoStr) {
        if (!isoStr) return '';
        const d = new Date(isoStr);
        return d.toLocaleDateString('en-IN', { day: '2-digit', month: 'short', year: 'numeric' });
      }

      function showToast(msg) {
        const el = document.getElementById('toast');
        el.textContent = msg;
        el.classList.remove('hidden');
        clearTimeout(window._toastTimer);
        window._toastTimer = setTimeout(() => el.classList.add('hidden'), 2800);
      }

      function createSampleEntries() {
        const now = new Date();
        const t1 = new Date(now.getTime() - 2.5 * 3600000).toISOString();
        const t2 = new Date(now.getTime() - 1.2 * 3600000).toISOString();
        const t3 = new Date(now.getTime() - 4.0 * 3600000).toISOString();
        const t3Out = new Date(now.getTime() - 2.1 * 3600000).toISOString();
        return [
          {
            id: 'sample_1',
            vehicleNo: 'MH 42 AQ 8412',
            vehicleType: 'Truck',
            driverName: 'Santosh Jadhav',
            driverMobile: '9822145670',
            partyName: 'Shree Balaji Edible Oils',
            category: 'Packaging / Oil',
            materialDetails: '150 Tins Palmolein Oil • Inv #884',
            readingUnit: 'KM',
            inReading: 45210,
            outReading: null,
            inTime: t1,
            outTime: null,
            outRemark: '',
            inPhoto: '',
            outPhoto: '',
            status: 'IN'
          },
          {
            id: 'sample_2',
            vehicleNo: 'MH 12 RN 3095',
            vehicleType: 'Tempo',
            driverName: 'Mahesh Pawar',
            driverMobile: '9765432109',
            partyName: 'Pune Supermart Distributors',
            category: 'Finished Goods',
            materialDetails: 'Loading Potato Chips & Moong Dal Cartons',
            readingUnit: 'KG',
            inReading: 3200,
            outReading: null,
            inTime: t2,
            outTime: null,
            outRemark: '',
            inPhoto: '',
            outPhoto: '',
            status: 'IN'
          },
          {
            id: 'sample_3',
            vehicleNo: 'MH 42 T 5519',
            vehicleType: 'Pickup',
            driverName: 'Ganesh Shinde',
            driverMobile: '9552110044',
            partyName: 'Kisan Agro Farms',
            category: 'Raw Material',
            materialDetails: '2.5 Ton Chipping Potatoes',
            readingUnit: 'KG',
            inReading: 4850,
            outReading: 2350,
            inTime: t3,
            outTime: t3Out,
            outRemark: 'Unloaded at Godown 2',
            inPhoto: '',
            outPhoto: '',
            status: 'OUT'
          }
        ];
      }

      function applyCompanyHeader() {
        document.getElementById('headerCompanyName').textContent = settings.companyName || 'Satvik Crunch Factory';
        document.getElementById('headerCompanyAddress').textContent = settings.companyAddress || 'Gate Security Register';
        const logoImg = document.getElementById('headerLogoImg');
        const logoDef = document.getElementById('headerLogoDefault');
        if (settings.companyLogo) {
          logoImg.src = settings.companyLogo;
          logoImg.classList.remove('hidden');
          logoDef.classList.add('hidden');
        } else {
          logoImg.classList.add('hidden');
          logoDef.classList.remove('hidden');
        }
      }

      function renderCompanyVehicles() {
        const list = settings.companyVehicles || [];
        const sel = document.getElementById('inSavedVehicleSelect');
        const currentVal = sel.value;
        sel.innerHTML = '<option value="">-- Outside Vehicle (Type Manually Below) --</option>' +
          list.map((v, idx) => `<option value="${idx}">${escapeHtml(v.no)} (${escapeHtml(v.type)})</option>`).join('');
        if (currentVal !== '' && list[Number(currentVal)]) sel.value = currentVal;

        const container = document.getElementById('compVehiclesList');
        if (list.length === 0) {
          container.innerHTML = '<p class="text-xs text-slate-400">No company vehicles added yet.</p>';
          return;
        }
        container.innerHTML = list.map((v, idx) => `
          <div class="flex items-center justify-between px-3 py-2 rounded-xl bg-slate-50 border border-slate-200 text-xs">
            <div><span class="font-bold text-slate-900">${escapeHtml(v.no)}</span> <span class="text-slate-500">(${escapeHtml(v.type)})</span></div>
            <button type="button" data-del-veh="${idx}" class="btn-del-comp-veh text-red-600 font-semibold hover:underline">Remove</button>
          </div>
        `).join('');
      }

      function renderCompanyDrivers() {
        const list = settings.companyDrivers || [];
        const sel = document.getElementById('inSavedDriverSelect');
        const currentVal = sel.value;
        sel.innerHTML = '<option value="">-- Outside Driver (Type Manually Below) --</option>' +
          list.map((d, idx) => `<option value="${idx}">${escapeHtml(d.name)}${d.mobile ? ' (' + escapeHtml(d.mobile) + ')' : ''}</option>`).join('');
        if (currentVal !== '' && list[Number(currentVal)]) sel.value = currentVal;

        const container = document.getElementById('compDriversList');
        if (list.length === 0) {
          container.innerHTML = '<p class="text-xs text-slate-400">No saved drivers added yet.</p>';
          return;
        }
        container.innerHTML = list.map((d, idx) => `
          <div class="flex items-center justify-between px-3 py-2 rounded-xl bg-slate-50 border border-slate-200 text-xs">
            <div><span class="font-bold text-slate-900">${escapeHtml(d.name)}</span> ${d.mobile ? `<span class="text-slate-500">(${escapeHtml(d.mobile)})</span>` : ''}</div>
            <button type="button" data-del-drv="${idx}" class="btn-del-comp-drv text-red-600 font-semibold hover:underline">Remove</button>
          </div>
        `).join('');
      }

      function setReturnMode(mode) {
        returnMode = mode;
        const btnEmpty = document.getElementById('btnRetEmpty');
        const btnMat = document.getElementById('btnRetWithMat');
        const sec = document.getElementById('retMaterialSection');
        if (mode === 'EMPTY') {
          btnEmpty.className = 'py-2 px-2 rounded-lg text-xs font-bold bg-blue-600 text-white shadow transition';
          btnMat.className = 'py-2 px-2 rounded-lg text-xs font-bold text-slate-600 hover:text-slate-900 transition';
          sec.classList.add('hidden');
        } else {
          btnMat.className = 'py-2 px-2 rounded-lg text-xs font-bold bg-blue-600 text-white shadow transition';
          btnEmpty.className = 'py-2 px-2 rounded-lg text-xs font-bold text-slate-600 hover:text-slate-900 transition';
          sec.classList.remove('hidden');
        }
      }

      function populateCompanyForm() {
        document.getElementById('setCompanyName').value = settings.companyName || '';
        document.getElementById('setCompanyAddress').value = settings.companyAddress || '';
        document.getElementById('setCompanyPhone').value = settings.companyPhone || '';
        document.getElementById('setCompanyGstin').value = settings.companyGstin || '';
        document.getElementById('setGuardName').value = settings.guardName || '';
        document.getElementById('setOwnerWhatsapp').value = settings.ownerWhatsapp || '';
        document.getElementById('setBackupEmail').value = settings.backupEmail || '';
        document.getElementById('setAutoPromptWa').checked = settings.autoPromptWa !== false;
        pendingLogoBase64 = settings.companyLogo || '';
        const wrap = document.getElementById('setLogoPreviewWrap');
        const img = document.getElementById('setLogoPreview');
        if (pendingLogoBase64) {
          img.src = pendingLogoBase64;
          wrap.classList.remove('hidden');
          wrap.classList.add('flex');
        } else {
          wrap.classList.add('hidden');
          wrap.classList.remove('flex');
        }
      }

      function loadState() {
        const savedSettings = safeGetStorage(SETTINGS_KEY);
        if (savedSettings) {
          try { settings = { ...settings, ...JSON.parse(savedSettings) }; } catch (e) {}
        }
        const savedEntries = safeGetStorage(STORAGE_KEY);
        if (savedEntries) {
          try { entries = JSON.parse(savedEntries); } catch (e) { entries = []; }
        } else {
          entries = createSampleEntries();
          safeSetStorage(STORAGE_KEY, JSON.stringify(entries));
        }
        applyCompanyHeader();
        populateCompanyForm();
        renderCompanyVehicles();
        renderCompanyDrivers();
        document.getElementById('reportDate').value = todayISO();
      }

      function saveEntries() {
        try {
          localStorage.setItem(STORAGE_KEY, JSON.stringify(entries));
        } catch (e) {
          // Prune oldest photos if storage quota is full so text entries always save
          for (let i = entries.length - 1; i >= 0; i--) {
            if (entries[i].inPhoto || entries[i].outPhoto) {
              entries[i].inPhoto = '';
              entries[i].outPhoto = '';
              try {
                localStorage.setItem(STORAGE_KEY, JSON.stringify(entries));
                showToast('Saved (cleared old photo cache for space)');
                return;
              } catch (e2) {}
            }
          }
          showToast('Saved in current session');
        }
      }

      function compressImage(file, maxW, callback) {
        const reader = new FileReader();
        reader.onload = function (ev) {
          const img = new Image();
          img.onload = function () {
            const scale = img.width > maxW ? maxW / img.width : 1;
            const canvas = document.createElement('canvas');
            canvas.width = Math.round(img.width * scale);
            canvas.height = Math.round(img.height * scale);
            const ctx = canvas.getContext('2d');
            ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
            callback(canvas.toDataURL('image/jpeg', 0.55));
          };
          img.src = ev.target.result;
        };
        reader.readAsDataURL(file);
      }

      function updateClocks() {
        const now = new Date();
        const t = now.toLocaleTimeString('en-IN', { hour: '2-digit', minute: '2-digit', hour12: true });
        document.getElementById('liveClock').textContent = t;
        document.getElementById('formAutoTime').textContent = t;
      }

      function setEntryMode(mode) {
        entryMode = mode;
        const btnIn = document.getElementById('btnModeIn');
        const btnOut = document.getElementById('btnModeOut');
        const badge = document.getElementById('formTimeBadge');
        const timeLbl = document.getElementById('formTimeLabel');
        const readLbl = document.getElementById('lblEntryReading');
        const subTxt = document.getElementById('btnSubmitEntryText');
        const submitBtn = document.querySelector('#vehicleInForm button[type="submit"]');

        if (mode === 'IN') {
          btnIn.className = 'py-2.5 px-3 rounded-lg text-xs sm:text-sm font-bold bg-emerald-600 text-white shadow transition';
          btnOut.className = 'py-2.5 px-3 rounded-lg text-xs sm:text-sm font-bold text-slate-600 hover:text-slate-900 transition';
          badge.className = 'px-2.5 py-1 rounded-lg bg-emerald-50 text-emerald-700 text-xs font-semibold border border-emerald-200';
          timeLbl.textContent = 'IN';
          readLbl.textContent = 'IN KM Reading';
          subTxt.textContent = 'Save Vehicle IN Entry';
          submitBtn.className = 'w-full py-3.5 px-4 rounded-xl bg-emerald-600 hover:bg-emerald-700 active:bg-emerald-800 text-white font-bold text-sm shadow-md transition flex items-center justify-center gap-2';
        } else {
          btnOut.className = 'py-2.5 px-3 rounded-lg text-xs sm:text-sm font-bold bg-orange-600 text-white shadow transition';
          btnIn.className = 'py-2.5 px-3 rounded-lg text-xs sm:text-sm font-bold text-slate-600 hover:text-slate-900 transition';
          badge.className = 'px-2.5 py-1 rounded-lg bg-orange-50 text-orange-700 text-xs font-semibold border border-orange-200';
          timeLbl.textContent = 'OUT';
          readLbl.textContent = 'OUT KM Reading';
          subTxt.textContent = 'Save Vehicle OUT Entry';
          submitBtn.className = 'w-full py-3.5 px-4 rounded-xl bg-orange-600 hover:bg-orange-700 active:bg-orange-800 text-white font-bold text-sm shadow-md transition flex items-center justify-center gap-2';
        }
      }

      function switchTab(tabName) {
        document.querySelectorAll('.nav-tab').forEach(btn => {
          btn.classList.toggle('bottom-tab-active', btn.dataset.tab === tabName);
        });
        document.querySelectorAll('.tab-view').forEach(sec => {
          sec.classList.toggle('hidden', sec.id !== `view-${tabName}`);
        });
        if (tabName === 'inside') renderInsideList();
        if (tabName === 'logs') renderLogsList();
        if (tabName === 'report') renderReport();
        if (tabName === 'company') populateCompanyForm();
        window.scrollTo({ top: 0, behavior: 'smooth' });
      }

      function updateCounts() {
        const insideCount = entries.filter(e => e.status === 'IN').length;
        document.getElementById('insideCountTop').textContent = insideCount;
        document.getElementById('insideCountTab').textContent = insideCount;
      }

      function escapeHtml(str) {
        return String(str || '').replace(/[&<>"']/g, s => ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', '"': '&quot;', "'": '&#39;' }[s]));
      }

      function renderCard(entry, showMarkOut) {
        const isIn = entry.status === 'IN';
        const isReturned = entry.status === 'RETURNED';
        const statusBadge = isIn
          ? `<span class="px-2 py-0.5 rounded-full text-[11px] font-bold bg-amber-100 text-amber-800 border border-amber-200">INSIDE</span>`
          : (isReturned
              ? `<span class="px-2 py-0.5 rounded-full text-[11px] font-bold bg-blue-100 text-blue-800 border border-blue-200">RETURNED</span>`
              : `<span class="px-2 py-0.5 rounded-full text-[11px] font-bold bg-emerald-100 text-emerald-800 border border-emerald-200">EXITED</span>`);

        const isOutFirst = entry.tripType === 'OUT_FIRST' || (entry.outTime && (!entry.inTime || new Date(entry.outTime) < new Date(entry.inTime)));
        let weightHtml = '';
        if (entry.materialWeight !== null && entry.materialWeight !== '' && !isNaN(entry.materialWeight)) {
          weightHtml = `<div class="text-xs text-blue-700 font-semibold">Material Weight: ${entry.materialWeight} ${escapeHtml(entry.weightUnit || 'KG')}</div>`;
        }
        if (entry.returnWithMaterial) {
          const rw = (entry.returnMaterialWeight !== null && entry.returnMaterialWeight !== '' && !isNaN(entry.returnMaterialWeight))
            ? ` • ${entry.returnMaterialWeight} ${escapeHtml(entry.returnWeightUnit || 'KG')}`
            : '';
          const fromTxt = entry.returnFromParty ? `From ${escapeHtml(entry.returnFromParty)} • ` : '';
          weightHtml += `<div class="text-xs text-emerald-700 font-semibold">Inward Pickup: ${fromTxt}${escapeHtml(entry.returnMaterialType)}${entry.returnMaterialDetails ? ' (' + escapeHtml(entry.returnMaterialDetails) + ')' : ''}${rw}</div>`;
        }
        let readingHtml = '';
        const unit = entry.readingUnit || 'KM';
        const hasInR = entry.inReading !== null && entry.inReading !== '' && !isNaN(entry.inReading);
        const hasOutR = entry.outReading !== null && entry.outReading !== '' && !isNaN(entry.outReading);
        if (hasInR && hasOutR) {
          const diff = Math.abs(Number(entry.outReading) - Number(entry.inReading));
          readingHtml = isOutFirst
            ? `<div class="text-xs text-slate-600"><span class="font-semibold">${unit}:</span> OUT ${entry.outReading} &rarr; Return IN ${entry.inReading} <span class="font-bold text-slate-800">(Net: ${diff} ${unit})</span></div>`
            : `<div class="text-xs text-slate-600"><span class="font-semibold">${unit}:</span> IN ${entry.inReading} &rarr; OUT ${entry.outReading} <span class="font-bold text-slate-800">(Net: ${diff} ${unit})</span></div>`;
        } else if (hasInR) {
          readingHtml = `<div class="text-xs text-slate-600"><span class="font-semibold">IN ${unit}:</span> ${entry.inReading}</div>`;
        } else if (hasOutR) {
          readingHtml = `<div class="text-xs text-slate-600"><span class="font-semibold">OUT ${unit}:</span> ${entry.outReading}</div>`;
        }

        const photoThumbs = [];
        if (entry.inPhoto) {
          photoThumbs.push(`<button type="button" data-photo-id="${entry.id}" data-photo-type="in" class="btn-view-photo inline-flex items-center gap-1 px-2.5 py-1.5 rounded-lg bg-slate-100 hover:bg-slate-200 text-[11px] font-semibold text-slate-700 border border-slate-200">IN Photo</button>`);
        }
        if (entry.outPhoto) {
          photoThumbs.push(`<button type="button" data-photo-id="${entry.id}" data-photo-type="out" class="btn-view-photo inline-flex items-center gap-1 px-2.5 py-1.5 rounded-lg bg-slate-100 hover:bg-slate-200 text-[11px] font-semibold text-slate-700 border border-slate-200">OUT Photo</button>`);
        }

        return `
          <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-4 space-y-2.5">
            <div class="flex items-start justify-between gap-2">
              <div>
                <div class="flex items-center gap-2 flex-wrap">
                  <span class="text-base font-extrabold text-slate-900 tracking-wide">${escapeHtml(entry.vehicleNo)}</span>
                  <span class="px-2 py-0.5 rounded-md bg-slate-100 text-slate-700 text-[11px] font-semibold">${escapeHtml(entry.vehicleType)}</span>
                  ${statusBadge}
                </div>
                <p class="text-xs font-semibold text-orange-700 mt-0.5">${escapeHtml(entry.partyName)} • ${escapeHtml(entry.category)}</p>
              </div>
              <div class="flex items-center gap-1">
                <button type="button" data-edit-id="${entry.id}" class="btn-edit-entry text-slate-400 hover:text-blue-600 p-1.5" title="Edit entry">
                  <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" />
                  </svg>
                </button>
                <button type="button" data-delete-id="${entry.id}" class="btn-delete-entry text-slate-400 hover:text-red-600 p-1.5" title="Delete entry">
                  <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
                  </svg>
                </button>
              </div>
            </div>

            <div class="text-xs text-slate-600 space-y-1">
              <div><span class="font-semibold text-slate-700">Driver:</span> ${escapeHtml(entry.driverName)} ${entry.driverMobile ? `(<a href="tel:${escapeHtml(entry.driverMobile)}" class="text-blue-600 font-semibold underline">${escapeHtml(entry.driverMobile)}</a>)` : ''}</div>
              ${entry.materialDetails ? `<div><span class="font-semibold text-slate-700">Details:</span> ${escapeHtml(entry.materialDetails)}</div>` : ''}
              ${weightHtml}
              ${readingHtml}
              ${entry.outRemark ? `<div><span class="font-semibold text-slate-700">OUT Note:</span> ${escapeHtml(entry.outRemark)}</div>` : ''}
            </div>

            <div class="flex items-center justify-between gap-2 pt-2 border-t border-slate-100 flex-wrap">
              <div class="text-[11px] text-slate-500">
                ${isOutFirst
                  ? `${entry.outTime ? `<span class="font-semibold text-slate-700">OUT:</span> ${formatDate(entry.outTime)}, ${formatTime(entry.outTime)}` : ''}
                     ${(entry.outTime && entry.inTime) ? '<br>' : ''}
                     ${entry.inTime ? `<span class="font-semibold text-slate-700">Return IN:</span> ${formatDate(entry.inTime)}, ${formatTime(entry.inTime)}` : ''}`
                  : `${entry.inTime ? `<span class="font-semibold text-slate-700">IN:</span> ${formatDate(entry.inTime)}, ${formatTime(entry.inTime)}` : ''}
                     ${(entry.inTime && entry.outTime) ? '<br>' : ''}
                     ${entry.outTime ? `<span class="font-semibold text-slate-700">OUT:</span> ${formatDate(entry.outTime)}, ${formatTime(entry.outTime)}` : ''}`
                }
              </div>
              <div class="flex items-center gap-2 flex-wrap">
                ${photoThumbs.join('')}
                <button type="button" data-share-id="${entry.id}" class="btn-share-entry px-2.5 py-1.5 rounded-lg bg-green-50 hover:bg-green-100 text-green-700 text-[11px] font-bold border border-green-200">
                  WhatsApp
                </button>
                ${(showMarkOut && isIn) ? `
                  <button type="button" data-checkout-id="${entry.id}" class="btn-mark-out px-4 py-2 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white text-xs font-bold shadow-sm transition">
                    Mark OUT &rarr;
                  </button>
                ` : ''}
                ${(entry.status === 'OUT' && !entry.inTime) ? `
                  <button type="button" data-return-id="${entry.id}" class="btn-mark-return px-3.5 py-2 rounded-xl bg-blue-600 hover:bg-blue-700 text-white text-xs font-bold shadow-sm transition">
                    Mark Return IN
                  </button>
                ` : ''}
              </div>
            </div>
          </div>
        `;
      }

      function renderInsideList() {
        const q = document.getElementById('insideSearch').value.trim().toLowerCase();
        const list = entries.filter(e => {
          if (e.status !== 'IN') return false;
          if (!q) return true;
          return `${e.vehicleNo} ${e.partyName} ${e.driverName} ${e.materialDetails}`.toLowerCase().includes(q);
        });
        const container = document.getElementById('insideList');
        if (list.length === 0) {
          container.innerHTML = `<div class="bg-white rounded-2xl p-8 text-center border border-slate-200 text-xs text-slate-500">No vehicles currently inside the gate.</div>`;
          return;
        }
        container.innerHTML = list.map(e => renderCard(e, true)).join('');
      }

      function renderLogsList() {
        const q = document.getElementById('logsSearch').value.trim().toLowerCase();
        const dateFilter = document.getElementById('filterDate').value;
        const statusFilter = document.getElementById('filterStatus').value;
        const catFilter = document.getElementById('filterCategory').value;

        const now = new Date();
        const todayStr = todayISO();
        const yest = new Date(now);
        yest.setDate(yest.getDate() - 1);
        const yestStr = `${yest.getFullYear()}-${String(yest.getMonth() + 1).padStart(2, '0')}-${String(yest.getDate()).padStart(2, '0')}`;
        const weekAgo = new Date(now.getTime() - 7 * 86400000);

        const list = entries.filter(e => {
          const refTime = e.inTime || e.outTime || '';
          const entryDate = toLocalDateISO(refTime);
          if (dateFilter === 'today' && entryDate !== todayStr) return false;
          if (dateFilter === 'yesterday' && entryDate !== yestStr) return false;
          if (dateFilter === '7days' && new Date(refTime) < weekAgo) return false;
          if (statusFilter !== 'all' && e.status !== statusFilter) return false;
          if (catFilter !== 'all' && e.category !== catFilter) return false;
          if (q && !`${e.vehicleNo} ${e.partyName} ${e.driverName} ${e.materialDetails}`.toLowerCase().includes(q)) return false;
          return true;
        });

        const container = document.getElementById('logsList');
        if (list.length === 0) {
          container.innerHTML = `<div class="bg-white rounded-2xl p-8 text-center border border-slate-200 text-xs text-slate-500">No matching vehicle entries found.</div>`;
          return;
        }
        container.innerHTML = list.map(e => renderCard(e, true)).join('');
      }

      function toKg(val, unit) {
        if (val === null || val === '' || isNaN(val)) return 0;
        const n = Number(val);
        if ((unit || 'KG') === 'TON') return n * 1000;
        if ((unit || 'KG') === 'KG') return n;
        return 0;
      }
      function calcRawMaterialInwardKg(e) {
        let total = 0;
        if (e.category === 'Raw Material') total += toKg(e.materialWeight, e.weightUnit);
        if (e.returnWithMaterial && e.returnMaterialType === 'Raw Material') {
          total += toKg(e.returnMaterialWeight, e.returnWeightUnit);
        }
        return total;
      }
      function calcWeightKg(e) {
        return toKg(e.materialWeight, e.weightUnit);
      }

      function buildWhatsAppText(dateStr) {
        const dayEntries = entries.filter(e => toLocalDateISO(e.inTime || e.outTime) === dateStr);
        const totalIn = dayEntries.length;
        const stillIn = dayEntries.filter(e => e.status === 'IN').length;
        const exited = dayEntries.filter(e => e.status === 'OUT' || e.status === 'RETURNED').length;
        const rawKg = dayEntries.reduce((sum, e) => sum + calcRawMaterialInwardKg(e), 0);
        const fgKg = dayEntries.filter(e => e.category === 'Finished Goods').reduce((sum, e) => sum + calcWeightKg(e), 0);
        const displayDate = dateStr.split('-').reverse().join('/');

        const lines = [
          `📋 *${(settings.companyName || 'Satvik Crunch Factory').toUpperCase()}*`,
          `*Daily Gate Report — ${displayDate}*`
        ];
        if (settings.companyAddress) lines.push(settings.companyAddress);
        lines.push(`Guard: ${settings.guardName || 'Security'}`);
        lines.push('');
        lines.push(`📊 *Summary*`);
        lines.push(`• Total Entries: *${totalIn}*`);
        lines.push(`• Inside Now: *${stillIn}*`);
        lines.push(`• Outside / Exited: *${exited}*`);
        if (rawKg > 0) lines.push(`• Raw Material Inward: *${rawKg.toLocaleString('en-IN')} KG*`);
        if (fgKg > 0) lines.push(`• Finished Goods Dispatch: *${fgKg.toLocaleString('en-IN')} KG*`);
        lines.push('──────────────────');

        if (dayEntries.length === 0) {
          lines.push('No vehicle entries recorded for this date.');
        } else {
          dayEntries.forEach((e, idx) => {
            const isOutFirst = e.tripType === 'OUT_FIRST' || (e.outTime && (!e.inTime || new Date(e.outTime) < new Date(e.inTime)));
            const statusIcon = e.status === 'IN' ? '🟡 INSIDE' : (e.status === 'RETURNED' ? '🔵 RETURNED' : '🟢 EXITED');
            const inTxt = e.inTime ? formatTime(e.inTime) : '--';
            const outTxt = e.outTime ? formatTime(e.outTime) : '--';
            lines.push('');
            lines.push(`*${idx + 1}. ${e.vehicleNo}* (${e.vehicleType}) — ${statusIcon}`);
            lines.push(`• *Party:* ${e.partyName}`);
            lines.push(`• *Purpose:* ${e.category}${e.materialDetails ? ' — ' + e.materialDetails : ''}`);
            if (e.materialWeight !== null && e.materialWeight !== '' && !isNaN(e.materialWeight)) {
              lines.push(`• *Weight/Qty:* ${e.materialWeight} ${e.weightUnit || 'KG'}`);
            }
            lines.push(`• *Driver:* ${e.driverName}${e.driverMobile ? ' (' + e.driverMobile + ')' : ''}`);
            if (isOutFirst) {
              lines.push(`• *OUT Time:* ${outTxt}${e.inTime ? ' | *Return IN:* ' + inTxt : ''}`);
            } else {
              lines.push(`• *IN Time:* ${inTxt}${e.outTime ? ' | *OUT:* ' + outTxt : ''}`);
            }
            const unit = e.readingUnit || 'KM';
            const hasInR = e.inReading !== null && e.inReading !== '' && !isNaN(e.inReading);
            const hasOutR = e.outReading !== null && e.outReading !== '' && !isNaN(e.outReading);
            if (hasInR && hasOutR) {
              const diff = Math.abs(Number(e.outReading) - Number(e.inReading));
              lines.push(isOutFirst
                ? `• *${unit}:* OUT ${e.outReading} -> Return IN ${e.inReading} (Net: ${diff})`
                : `• *${unit}:* IN ${e.inReading} -> OUT ${e.outReading} (Net: ${diff})`);
            } else if (hasOutR) {
              lines.push(`• *OUT ${unit}:* ${e.outReading}`);
            } else if (hasInR) {
              lines.push(`• *IN ${unit}:* ${e.inReading}`);
            }
          });
        }
        return lines.join('\n');
      }

      function renderReport() {
        const dateStr = document.getElementById('reportDate').value || todayISO();
        const dayEntries = entries.filter(e => toLocalDateISO(e.inTime || e.outTime) === dateStr);
        document.getElementById('repTotalIn').textContent = dayEntries.length;
        document.getElementById('repStillIn').textContent = dayEntries.filter(e => e.status === 'IN').length;
        document.getElementById('repExited').textContent = dayEntries.filter(e => e.status === 'OUT' || e.status === 'RETURNED').length;
        const rawKg = dayEntries.reduce((sum, e) => sum + calcRawMaterialInwardKg(e), 0);
        document.getElementById('repRawKg').textContent = `${rawKg.toLocaleString('en-IN')} KG`;
        document.getElementById('whatsappPreview').value = buildWhatsAppText(dateStr);
      }

      function openCheckoutModal(id) {
        const entry = entries.find(e => e.id === id);
        if (!entry) return;
        document.getElementById('outEntryId').value = entry.id;
        document.getElementById('outVehicleSummary').textContent = `${entry.vehicleNo} (${entry.vehicleType}) • ${entry.partyName}`;
        document.getElementById('outReadingUnitLabel').textContent = entry.readingUnit || 'KM';
        document.getElementById('outReadingVal').value = '';
        document.getElementById('outRemark').value = '';
        outPhotoBase64 = '';
        document.getElementById('outPhotoPreview').classList.add('hidden');
        document.getElementById('checkoutModal').classList.remove('hidden');
        document.getElementById('checkoutModal').classList.add('flex');
      }

      function openReturnInModal(id) {
        const entry = entries.find(e => e.id === id);
        if (!entry) return;
        document.getElementById('retEntryId').value = entry.id;
        document.getElementById('retVehicleSummary').textContent = `${entry.vehicleNo} (${entry.vehicleType}) • ${entry.partyName}`;
        document.getElementById('retReadingUnitLabel').textContent = entry.readingUnit || 'KM';
        document.getElementById('retReadingVal').value = '';
        document.getElementById('retRemark').value = '';
        document.getElementById('retFromParty').value = '';
        document.getElementById('retMatDetails').value = '';
        document.getElementById('retMatWeight').value = '';
        setReturnMode('EMPTY');
        retPhotoBase64 = '';
        document.getElementById('retPhotoInput').value = '';
        document.getElementById('retPhotoPreview').classList.add('hidden');
        document.getElementById('returnInModal').classList.remove('hidden');
        document.getElementById('returnInModal').classList.add('flex');
      }

      function closeReturnInModal() {
        document.getElementById('returnInModal').classList.add('hidden');
        document.getElementById('returnInModal').classList.remove('flex');
      }

      function closeCheckoutModal() {
        document.getElementById('checkoutModal').classList.add('hidden');
        document.getElementById('checkoutModal').classList.remove('flex');
      }

      function openEditModal(id) {
        const entry = entries.find(e => e.id === id);
        if (!entry) return;
        document.getElementById('editEntryId').value = entry.id;
        document.getElementById('editVehicleNo').value = entry.vehicleNo;
        document.getElementById('editVehicleType').value = entry.vehicleType;
        document.getElementById('editDriverName').value = entry.driverName;
        document.getElementById('editDriverMobile').value = entry.driverMobile || '';
        document.getElementById('editPartyName').value = entry.partyName;
        document.getElementById('editMaterialDetails').value = entry.materialDetails || '';
        document.getElementById('editInReading').value = entry.inReading ?? '';
        document.getElementById('editOutReading').value = entry.outReading ?? '';
        document.getElementById('editModal').classList.remove('hidden');
        document.getElementById('editModal').classList.add('flex');
      }

      function closeEditModal() {
        document.getElementById('editModal').classList.add('hidden');
        document.getElementById('editModal').classList.remove('flex');
      }

      function buildSingleEntryWhatsAppText(entry) {
        const isOut = entry.status === 'OUT';
        const isReturned = entry.status === 'RETURNED';
        const isOutFirst = entry.tripType === 'OUT_FIRST' || (entry.outTime && (!entry.inTime || new Date(entry.outTime) < new Date(entry.inTime)));
        const isReturnInSlip = isReturned || (!isOut && isOutFirst);
        const tag = isOut
          ? '🟢 GATE OUT SLIP'
          : (isReturnInSlip ? '🔵 GATE RETURN IN SLIP' : '🟡 GATE IN SLIP');
        const lines = [
          `🚛 *${(settings.companyName || 'Satvik Crunch Factory').toUpperCase()}*`,
          `*${tag}*`,
          '──────────────────',
          `*Vehicle No:* ${entry.vehicleNo} (${entry.vehicleType})`,
          `*Party:* ${entry.partyName}`,
          `*Purpose:* ${entry.category}`
        ];
        if (entry.materialDetails) lines.push(`*Details:* ${entry.materialDetails}`);
        if (!isReturnInSlip && entry.materialWeight !== null && entry.materialWeight !== '' && !isNaN(entry.materialWeight)) {
          lines.push(`*Material Weight:* ${entry.materialWeight} ${entry.weightUnit || 'KG'}`);
        }
        if (isReturnInSlip && entry.returnWithMaterial) {
          lines.push('');
          lines.push(`📥 *INWARD PICKUP DETAILS:*`);
          if (entry.returnFromParty) lines.push(`*From Party:* ${entry.returnFromParty}`);
          lines.push(`*Inward Purpose:* ${entry.returnMaterialType}`);
          if (entry.returnMaterialDetails) lines.push(`*Material:* ${entry.returnMaterialDetails}`);
          if (entry.returnMaterialWeight !== null && entry.returnMaterialWeight !== '' && !isNaN(entry.returnMaterialWeight)) {
            lines.push(`*Weight:* ${entry.returnMaterialWeight} ${entry.returnWeightUnit || 'KG'}`);
          }
        }
        lines.push('');
        lines.push(`*Driver:* ${entry.driverName}`);
        if (entry.driverMobile) lines.push(`*Mobile:* ${entry.driverMobile}`);
        lines.push('');

        const unit = entry.readingUnit || 'KM';
        const hasInR = entry.inReading !== null && entry.inReading !== '' && !isNaN(entry.inReading);
        const hasOutR = entry.outReading !== null && entry.outReading !== '' && !isNaN(entry.outReading);

        if (isOutFirst) {
          if (entry.outTime) lines.push(`*OUT Time:* ${formatDate(entry.outTime)}, ${formatTime(entry.outTime)}`);
          if (hasOutR) lines.push(`*OUT ${unit}:* ${entry.outReading}`);
          if (entry.inTime) {
            lines.push(`*Return IN Time:* ${formatDate(entry.inTime)}, ${formatTime(entry.inTime)}`);
            if (hasInR) lines.push(`*Return IN ${unit}:* ${entry.inReading}`);
          }
          if (hasOutR && hasInR) {
            const diff = Math.abs(Number(entry.inReading) - Number(entry.outReading));
            lines.push(`*Total Run:* ${diff} ${unit}`);
          }
        } else {
          if (entry.inTime) lines.push(`*IN Time:* ${formatDate(entry.inTime)}, ${formatTime(entry.inTime)}`);
          if (hasInR) lines.push(`*IN ${unit}:* ${entry.inReading}`);
          if (entry.outTime) {
            lines.push(`*OUT Time:* ${formatDate(entry.outTime)}, ${formatTime(entry.outTime)}`);
            if (hasOutR) lines.push(`*OUT ${unit}:* ${entry.outReading}`);
          }
          if (hasInR && hasOutR) {
            const diff = Math.abs(Number(entry.outReading) - Number(entry.inReading));
            lines.push(`*Net ${unit}:* ${diff} ${unit}`);
          }
        }
        if (entry.outRemark) lines.push(`*OUT Note:* ${entry.outRemark}`);
        lines.push('──────────────────');
        lines.push(`*Guard:* ${settings.guardName || 'Security'}`);
        return lines.join('\n');
      }

      let currentWaEntry = null;

      function openSingleWaModal(entry) {
        currentWaEntry = entry;
        document.getElementById('waSingleTitle').textContent = entry.status === 'OUT'
          ? `Vehicle OUT — Send to WhatsApp Group`
          : `Vehicle IN — Send to WhatsApp Group`;
        document.getElementById('waSingleText').value = buildSingleEntryWhatsAppText(entry);
        const photoSrc = (entry.status === 'OUT' && entry.outPhoto) ? entry.outPhoto : (entry.inPhoto || entry.outPhoto || '');
        const photoRow = document.getElementById('waSinglePhotoRow');
        if (photoSrc) {
          document.getElementById('waSinglePhotoThumb').src = photoSrc;
          photoRow.classList.remove('hidden');
          photoRow.classList.add('flex');
        } else {
          photoRow.classList.add('hidden');
          photoRow.classList.remove('flex');
        }
        document.getElementById('waSingleModal').classList.remove('hidden');
        document.getElementById('waSingleModal').classList.add('flex');
      }

      function shareSingleSlipImage(entry) {
        if (!entry) return;
        const canvas = document.createElement('canvas');
        canvas.width = 720;
        canvas.height = 680;
        const ctx = canvas.getContext('2d');

        ctx.fillStyle = '#ffffff';
        ctx.fillRect(0, 0, canvas.width, canvas.height);

        // Header
        ctx.fillStyle = '#0f172a';
        ctx.fillRect(0, 0, canvas.width, 115);
        ctx.fillStyle = '#ffffff';
        ctx.font = 'bold 28px Inter, sans-serif';
        ctx.fillText((settings.companyName || 'Satvik Crunch Factory').toUpperCase(), 32, 52);
        ctx.fillStyle = '#cbd5e1';
        ctx.font = '18px Inter, sans-serif';
        ctx.fillText(settings.companyAddress || 'Gate Security Register', 32, 85);

        // Status Pill
        const isOut = entry.status === 'OUT';
        ctx.fillStyle = isOut ? '#059669' : '#d97706';
        ctx.fillRect(520, 34, 168, 46);
        ctx.fillStyle = '#ffffff';
        ctx.font = 'bold 20px Inter, sans-serif';
        ctx.fillText(isOut ? 'GATE OUT' : 'GATE IN', 554, 64);

        // Rows
        const rows = [
          ['Vehicle No', `${entry.vehicleNo} (${entry.vehicleType})`],
          ['Party Name', entry.partyName],
          ['Purpose', entry.category],
          ['Details', entry.materialDetails || '-'],
          ['Driver', `${entry.driverName}${entry.driverMobile ? ' (' + entry.driverMobile + ')' : ''}`],
          ['IN Time', entry.inTime ? `${formatDate(entry.inTime)}, ${formatTime(entry.inTime)}` : 'Direct Dispatch (OUT)'],
          ['OUT Time', entry.outTime ? `${formatDate(entry.outTime)}, ${formatTime(entry.outTime)}` : 'Still Inside']
        ];
        if (entry.inReading !== null && entry.inReading !== '' && !isNaN(entry.inReading)) {
          const unit = entry.readingUnit || 'KM';
          const outR = (isOut && entry.outReading !== null && entry.outReading !== '') ? ` -> OUT ${entry.outReading}` : '';
          rows.push([`${unit} Reading`, `IN ${entry.inReading}${outR}`]);
        }
        if (isOut && entry.outRemark) rows.push(['OUT Note', entry.outRemark]);
        rows.push(['Guard', settings.guardName || 'Security']);

        let y = 165;
        rows.forEach(([k, v], i) => {
          if (i % 2 === 0) {
            ctx.fillStyle = '#f8fafc';
            ctx.fillRect(28, y - 30, 664, 44);
          }
          ctx.fillStyle = '#64748b';
          ctx.font = 'bold 18px Inter, sans-serif';
          ctx.fillText(k, 40, y);
          ctx.fillStyle = '#0f172a';
          ctx.font = '600 18px Inter, sans-serif';
          ctx.fillText(String(v).slice(0, 44), 210, y);
          y += 48;
        });

        const photoSrc = (entry.status === 'OUT' && entry.outPhoto) ? entry.outPhoto : (entry.inPhoto || entry.outPhoto || '');

        function finalizeAndShare(targetCanvas) {
          const reportText = buildSingleEntryWhatsAppText(entry);
          targetCanvas.toBlob(async (blob) => {
            if (!blob) return;
            const file = new File([blob], `gate_slip_${entry.vehicleNo.replace(/\s+/g, '_')}.png`, { type: 'image/png' });
            if (navigator.canShare && navigator.canShare({ files: [file] })) {
              try {
                await navigator.share({
                  files: [file],
                  text: reportText,
                  title: `${entry.vehicleNo} Gate Report`
                });
                return;
              } catch (err) {}
            }
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = file.name;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
            showToast('Gate Slip + Photo PNG downloaded!');
          }, 'image/png');
        }

        if (photoSrc) {
          const img = new Image();
          img.onload = function () {
            const maxW = 664;
            const maxH = 380;
            const ratio = Math.min(maxW / img.width, maxH / img.height, 1);
            const drawW = Math.round(img.width * ratio);
            const drawH = Math.round(img.height * ratio);

            const fullCanvas = document.createElement('canvas');
            fullCanvas.width = 720;
            fullCanvas.height = y + 36 + drawH + 30;
            const fctx = fullCanvas.getContext('2d');
            fctx.fillStyle = '#ffffff';
            fctx.fillRect(0, 0, fullCanvas.width, fullCanvas.height);
            fctx.drawImage(canvas, 0, 0);

            fctx.fillStyle = '#475569';
            fctx.font = 'bold 16px Inter, sans-serif';
            fctx.fillText('ATTACHED VEHICLE / BILL PHOTO:', 32, y + 18);
            const xPos = Math.round((720 - drawW) / 2);
            fctx.drawImage(img, xPos, y + 32, drawW, drawH);
            finalizeAndShare(fullCanvas);
          };
          img.onerror = function () { finalizeAndShare(canvas); };
          img.src = photoSrc;
        } else {
          finalizeAndShare(canvas);
        }
      }

      function closeSingleWaModal() {
        document.getElementById('waSingleModal').classList.add('hidden');
        document.getElementById('waSingleModal').classList.remove('flex');
      }

      function openConfirm(title, message, cb) {
        document.getElementById('confirmTitle').textContent = title;
        document.getElementById('confirmMessage').textContent = message;
        confirmCallback = cb;
        document.getElementById('confirmModal').classList.remove('hidden');
        document.getElementById('confirmModal').classList.add('flex');
      }

      function closeConfirm() {
        document.getElementById('confirmModal').classList.add('hidden');
        document.getElementById('confirmModal').classList.remove('flex');
        confirmCallback = null;
      }

      // Navigation Listeners
      document.querySelectorAll('.nav-tab').forEach(btn => {
        btn.addEventListener('click', () => switchTab(btn.dataset.tab));
      });
      document.getElementById('btnHeaderEditCompany').addEventListener('click', () => switchTab('company'));
      document.getElementById('inSavedVehicleSelect').addEventListener('change', function () {
        const idx = this.value;
        if (idx === '') return;
        const v = (settings.companyVehicles || [])[Number(idx)];
        if (v) {
          document.getElementById('inVehicleNo').value = v.no;
          document.getElementById('inVehicleType').value = v.type;
        }
      });

      document.getElementById('inSavedDriverSelect').addEventListener('change', function () {
        const idx = this.value;
        if (idx === '') return;
        const d = (settings.companyDrivers || [])[Number(idx)];
        if (d) {
          document.getElementById('inDriverName').value = d.name;
          document.getElementById('inDriverMobile').value = d.mobile || '';
        }
      });

      document.getElementById('btnQuickAddDriver').addEventListener('click', () => {
        switchTab('company');
        setTimeout(() => document.getElementById('newCompDriverName').focus(), 200);
      });

      document.getElementById('btnAddCompDriver').addEventListener('click', () => {
        const name = document.getElementById('newCompDriverName').value.trim();
        const mobile = document.getElementById('newCompDriverMobile').value.trim();
        if (!name) { showToast('Enter driver name first'); return; }
        settings.companyDrivers = settings.companyDrivers || [];
        if (settings.companyDrivers.some(d => d.name.toLowerCase() === name.toLowerCase())) {
          showToast('Driver already in list');
          return;
        }
        settings.companyDrivers.push({ name, mobile });
        safeSetStorage(SETTINGS_KEY, JSON.stringify(settings));
        document.getElementById('newCompDriverName').value = '';
        document.getElementById('newCompDriverMobile').value = '';
        renderCompanyDrivers();
        showToast(`${name} added to drivers list`);
      });

      document.getElementById('compDriversList').addEventListener('click', (e) => {
        const btn = e.target.closest('.btn-del-comp-drv');
        if (!btn) return;
        const idx = Number(btn.dataset.delDrv);
        settings.companyDrivers.splice(idx, 1);
        safeSetStorage(SETTINGS_KEY, JSON.stringify(settings));
        renderCompanyDrivers();
        showToast('Driver removed');
      });

      document.getElementById('btnRetEmpty').addEventListener('click', () => setReturnMode('EMPTY'));
      document.getElementById('btnRetWithMat').addEventListener('click', () => setReturnMode('MATERIAL'));

      document.getElementById('btnQuickAddVehicle').addEventListener('click', () => {
        switchTab('company');
        setTimeout(() => document.getElementById('newCompVehNo').focus(), 200);
      });

      document.getElementById('btnAddCompVehicle').addEventListener('click', () => {
        const no = document.getElementById('newCompVehNo').value.trim().toUpperCase();
        const type = document.getElementById('newCompVehType').value;
        if (!no) { showToast('Enter vehicle number first'); return; }
        settings.companyVehicles = settings.companyVehicles || [];
        if (settings.companyVehicles.some(v => v.no === no)) {
          showToast('Vehicle already in list');
          return;
        }
        settings.companyVehicles.push({ no, type });
        safeSetStorage(SETTINGS_KEY, JSON.stringify(settings));
        document.getElementById('newCompVehNo').value = '';
        renderCompanyVehicles();
        showToast(`${no} added to company vehicles`);
      });

      document.getElementById('compVehiclesList').addEventListener('click', (e) => {
        const btn = e.target.closest('.btn-del-comp-veh');
        if (!btn) return;
        const idx = Number(btn.dataset.delVeh);
        settings.companyVehicles.splice(idx, 1);
        safeSetStorage(SETTINGS_KEY, JSON.stringify(settings));
        renderCompanyVehicles();
        showToast('Vehicle removed');
      });

      document.getElementById('btnModeIn').addEventListener('click', () => setEntryMode('IN'));
      document.getElementById('btnModeOut').addEventListener('click', () => setEntryMode('OUT'));

      // Photo Inputs
      document.getElementById('inPhotoInput').addEventListener('change', function (e) {
        const file = e.target.files[0];
        if (!file) return;
        compressImage(file, 450, dataUrl => {
          inPhotoBase64 = dataUrl;
          document.getElementById('inPhotoPreview').src = dataUrl;
          document.getElementById('inPhotoPreviewWrap').classList.remove('hidden');
          document.getElementById('inPhotoPreviewWrap').classList.add('flex');
        });
      });

      document.getElementById('btnClearInPhoto').addEventListener('click', () => {
        inPhotoBase64 = '';
        document.getElementById('inPhotoInput').value = '';
        document.getElementById('inPhotoPreviewWrap').classList.add('hidden');
        document.getElementById('inPhotoPreviewWrap').classList.remove('flex');
      });

      document.getElementById('outPhotoInput').addEventListener('change', function (e) {
        const file = e.target.files[0];
        if (!file) return;
        compressImage(file, 450, dataUrl => {
          outPhotoBase64 = dataUrl;
          const img = document.getElementById('outPhotoPreview');
          img.src = dataUrl;
          img.classList.remove('hidden');
        });
      });

      document.getElementById('setLogoInput').addEventListener('change', function (e) {
        const file = e.target.files[0];
        if (!file) return;
        compressImage(file, 200, dataUrl => {
          pendingLogoBase64 = dataUrl;
          document.getElementById('setLogoPreview').src = dataUrl;
          document.getElementById('setLogoPreviewWrap').classList.remove('hidden');
          document.getElementById('setLogoPreviewWrap').classList.add('flex');
        });
      });

      document.getElementById('btnClearLogo').addEventListener('click', () => {
        pendingLogoBase64 = '';
        document.getElementById('setLogoInput').value = '';
        document.getElementById('setLogoPreviewWrap').classList.add('hidden');
        document.getElementById('setLogoPreviewWrap').classList.remove('flex');
      });

      // Forms
      document.getElementById('vehicleInForm').addEventListener('submit', function (e) {
        e.preventDefault();
        const vNo = document.getElementById('inVehicleNo').value.trim().toUpperCase();
        if (!vNo) return;

        const nowIso = new Date().toISOString();
        const rVal = document.getElementById('inReadingVal').value !== '' ? Number(document.getElementById('inReadingVal').value) : null;
        const isOutMode = entryMode === 'OUT';

        const wVal = document.getElementById('inMaterialWeight').value !== '' ? Number(document.getElementById('inMaterialWeight').value) : null;
        const wUnit = document.getElementById('inWeightUnit').value;
        const newEntry = {
          id: 'ent_' + Date.now(),
          tripType: isOutMode ? 'OUT_FIRST' : 'IN_FIRST',
          vehicleNo: vNo,
          vehicleType: document.getElementById('inVehicleType').value,
          driverName: document.getElementById('inDriverName').value.trim(),
          driverMobile: document.getElementById('inDriverMobile').value.trim(),
          partyName: document.getElementById('inPartyName').value.trim(),
          category: document.getElementById('inCategory').value,
          materialDetails: document.getElementById('inMaterialDetails').value.trim(),
          materialWeight: wVal,
          weightUnit: wUnit,
          readingUnit: document.getElementById('inReadingUnit').value,
          inReading: isOutMode ? null : rVal,
          outReading: isOutMode ? rVal : null,
          inTime: isOutMode ? null : nowIso,
          outTime: isOutMode ? nowIso : null,
          outRemark: '',
          inPhoto: isOutMode ? '' : inPhotoBase64,
          outPhoto: isOutMode ? inPhotoBase64 : '',
          status: isOutMode ? 'OUT' : 'IN'
        };

        entries.unshift(newEntry);
        saveEntries();
        updateCounts();
        renderInsideList();
        renderLogsList();
        renderReport();
        this.reset();
        inPhotoBase64 = '';
        document.getElementById('inPhotoPreviewWrap').classList.add('hidden');
        document.getElementById('inPhotoPreviewWrap').classList.remove('flex');
        showToast(`Saved ${entryMode} entry for ${vNo}`);
        if (settings.autoPromptWa !== false) {
          openSingleWaModal(newEntry);
        }
      });

      document.getElementById('checkoutForm').addEventListener('submit', function (e) {
        e.preventDefault();
        const id = document.getElementById('outEntryId').value;
        const entry = entries.find(item => item.id === id);
        if (!entry) return;
        const outVal = document.getElementById('outReadingVal').value;
        entry.outReading = outVal !== '' ? Number(outVal) : null;
        entry.outRemark = document.getElementById('outRemark').value.trim();
        entry.outPhoto = outPhotoBase64;
        entry.outTime = new Date().toISOString();
        entry.status = 'OUT';
        saveEntries();
        updateCounts();
        closeCheckoutModal();
        renderInsideList();
        renderLogsList();
        showToast(`${entry.vehicleNo} marked OUT`);
        if (settings.autoPromptWa !== false) {
          openSingleWaModal(entry);
        }
      });

      document.getElementById('editForm').addEventListener('submit', function (e) {
        e.preventDefault();
        const id = document.getElementById('editEntryId').value;
        const entry = entries.find(item => item.id === id);
        if (!entry) return;
        entry.vehicleNo = document.getElementById('editVehicleNo').value.trim().toUpperCase();
        entry.vehicleType = document.getElementById('editVehicleType').value;
        entry.driverName = document.getElementById('editDriverName').value.trim();
        entry.driverMobile = document.getElementById('editDriverMobile').value.trim();
        entry.partyName = document.getElementById('editPartyName').value.trim();
        entry.materialDetails = document.getElementById('editMaterialDetails').value.trim();
        const inR = document.getElementById('editInReading').value;
        const outR = document.getElementById('editOutReading').value;
        entry.inReading = inR !== '' ? Number(inR) : null;
        entry.outReading = outR !== '' ? Number(outR) : null;
        saveEntries();
        closeEditModal();
        renderInsideList();
        renderLogsList();
        renderReport();
        showToast('Entry updated');
      });

      document.getElementById('companySettingsForm').addEventListener('submit', function (e) {
        e.preventDefault();
        settings.companyName = document.getElementById('setCompanyName').value.trim() || 'Satvik Crunch Factory';
        settings.companyAddress = document.getElementById('setCompanyAddress').value.trim();
        settings.companyPhone = document.getElementById('setCompanyPhone').value.trim();
        settings.companyGstin = document.getElementById('setCompanyGstin').value.trim();
        settings.guardName = document.getElementById('setGuardName').value.trim() || 'Main Gate Security';
        settings.ownerWhatsapp = document.getElementById('setOwnerWhatsapp').value.trim();
        settings.backupEmail = document.getElementById('setBackupEmail').value.trim();
        settings.autoPromptWa = document.getElementById('setAutoPromptWa').checked;
        settings.companyLogo = pendingLogoBase64;
        safeSetStorage(SETTINGS_KEY, JSON.stringify(settings));
        applyCompanyHeader();
        renderReport();
        showToast('Company details saved!');
      });

      document.getElementById('retPhotoInput').addEventListener('change', function (e) {
        const file = e.target.files[0];
        if (!file) return;
        compressImage(file, 450, dataUrl => {
          retPhotoBase64 = dataUrl;
          const img = document.getElementById('retPhotoPreview');
          img.src = dataUrl;
          img.classList.remove('hidden');
        });
      });

      document.getElementById('returnInForm').addEventListener('submit', function (e) {
        e.preventDefault();
        const id = document.getElementById('retEntryId').value;
        const entry = entries.find(item => item.id === id);
        if (!entry) return;
        const retVal = document.getElementById('retReadingVal').value;
        if (retVal !== '') entry.inReading = Number(retVal);
        const note = document.getElementById('retRemark').value.trim();
        if (note) {
          entry.materialDetails = entry.materialDetails ? `${entry.materialDetails} | Return: ${note}` : `Return: ${note}`;
        }
        if (returnMode === 'MATERIAL') {
          entry.returnWithMaterial = true;
          entry.returnFromParty = document.getElementById('retFromParty').value.trim();
          entry.returnMaterialType = document.getElementById('retMatType').value;
          entry.returnMaterialDetails = document.getElementById('retMatDetails').value.trim();
          const mw = document.getElementById('retMatWeight').value;
          entry.returnMaterialWeight = mw !== '' ? Number(mw) : null;
          entry.returnWeightUnit = document.getElementById('retMatUnit').value;
        } else {
          entry.returnWithMaterial = false;
          entry.returnMaterialType = '';
          entry.returnMaterialDetails = '';
          entry.returnMaterialWeight = null;
        }
        if (retPhotoBase64) entry.inPhoto = retPhotoBase64;
        entry.inTime = new Date().toISOString();
        entry.status = 'RETURNED';
        saveEntries();
        updateCounts();
        closeReturnInModal();
        renderInsideList();
        renderLogsList();
        renderReport();
        showToast(`${entry.vehicleNo} marked Return IN`);
        if (settings.autoPromptWa !== false) {
          openSingleWaModal(entry);
        }
      });

      document.getElementById('btnCloseReturn').addEventListener('click', closeReturnInModal);
      document.getElementById('btnCancelReturn').addEventListener('click', closeReturnInModal);

      document.getElementById('btnCloseCheckout').addEventListener('click', closeCheckoutModal);
      document.getElementById('btnCancelCheckout').addEventListener('click', closeCheckoutModal);
      document.getElementById('btnCloseEdit').addEventListener('click', closeEditModal);
      document.getElementById('btnCancelEdit').addEventListener('click', closeEditModal);

      // Event delegation for card buttons
      document.addEventListener('click', function (e) {
        const outBtn = e.target.closest('.btn-mark-out');
        if (outBtn) { openCheckoutModal(outBtn.dataset.checkoutId); return; }

        const retBtn = e.target.closest('.btn-mark-return');
        if (retBtn) {
          openReturnInModal(retBtn.dataset.returnId);
          return;
        }

        const shareBtn = e.target.closest('.btn-share-entry');
        if (shareBtn) {
          const item = entries.find(x => x.id === shareBtn.dataset.shareId);
          if (item) openSingleWaModal(item);
          return;
        }

        const editBtn = e.target.closest('.btn-edit-entry');
        if (editBtn) { openEditModal(editBtn.dataset.editId); return; }

        const delBtn = e.target.closest('.btn-delete-entry');
        if (delBtn) {
          const id = delBtn.dataset.deleteId;
          const item = entries.find(x => x.id === id);
          if (!item) return;
          openConfirm('Delete Entry?', `Remove ${item.vehicleNo} (${item.partyName}) from register?`, () => {
            entries = entries.filter(x => x.id !== id);
            saveEntries();
            updateCounts();
            renderInsideList();
            renderLogsList();
            renderReport();
            showToast('Entry deleted');
          });
          return;
        }
        const photoBtn = e.target.closest('.btn-view-photo');
        if (photoBtn) {
          const item = entries.find(x => x.id === photoBtn.dataset.photoId);
          if (!item) return;
          const src = photoBtn.dataset.photoType === 'out' ? item.outPhoto : item.inPhoto;
          if (!src) return;
          document.getElementById('photoModalTitle').textContent = `${item.vehicleNo} — ${photoBtn.dataset.photoType.toUpperCase()} Photo`;
          document.getElementById('photoModalImg').src = src;
          document.getElementById('photoModal').classList.remove('hidden');
          document.getElementById('photoModal').classList.add('flex');
        }
      });

      document.getElementById('btnClosePhoto').addEventListener('click', () => {
        document.getElementById('photoModal').classList.add('hidden');
        document.getElementById('photoModal').classList.remove('flex');
      });

      document.getElementById('insideSearch').addEventListener('input', renderInsideList);
      document.getElementById('logsSearch').addEventListener('input', renderLogsList);
      document.getElementById('filterDate').addEventListener('change', renderLogsList);
      document.getElementById('filterStatus').addEventListener('change', renderLogsList);
      document.getElementById('filterCategory').addEventListener('change', renderLogsList);
      document.getElementById('reportDate').addEventListener('change', renderReport);

      document.getElementById('btnShareWhatsApp').addEventListener('click', () => {
        const text = document.getElementById('whatsappPreview').value;
        const phone = (settings.ownerWhatsapp || '').replace(/\D/g, '');
        const base = phone ? `https://wa.me/${phone}?text=` : `https://wa.me/?text=`;
        window.open(base + encodeURIComponent(text), '_blank');
      });

      document.getElementById('btnCopyReport').addEventListener('click', () => {
        const ta = document.getElementById('whatsappPreview');
        if (navigator.clipboard && navigator.clipboard.writeText) {
          navigator.clipboard.writeText(ta.value).then(() => showToast('Report copied for WhatsApp!')).catch(() => {
            ta.select();
            document.execCommand('copy');
            showToast('Report copied!');
          });
        } else {
          ta.select();
          document.execCommand('copy');
          showToast('Report copied!');
        }
      });

      function sendBackupViaEmail(reportOnlyDate) {
        const email = (settings.backupEmail || '').trim();
        if (!email) {
          showToast('Please save your Backup Email in Company tab first!');
          switchTab('company');
          setTimeout(() => document.getElementById('setBackupEmail').focus(), 200);
          return;
        }
        const dateStr = reportOnlyDate || todayISO();
        const subject = `${settings.companyName || 'Satvik Crunch Factory'} — Gate Register Backup (${dateStr})`;
        let body = '';
        if (reportOnlyDate) {
          body = buildWhatsAppText(reportOnlyDate);
        } else {
          body = `${settings.companyName} — Full Gate Register Backup (${entries.length} entries)\n\n` +
            entries.slice(0, 40).map((e, i) =>
              `${i + 1}. ${e.vehicleNo} (${e.vehicleType}) | ${e.status} | ${e.partyName} | ${e.category} | Driver: ${e.driverName} | IN: ${e.inTime ? formatDate(e.inTime) + ' ' + formatTime(e.inTime) : '-'} | OUT: ${e.outTime ? formatDate(e.outTime) + ' ' + formatTime(e.outTime) : '-'}`
            ).join('\n');
        }
        window.location.href = `mailto:${encodeURIComponent(email)}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
      }

      document.getElementById('btnEmailReport').addEventListener('click', () => {
        sendBackupViaEmail(document.getElementById('reportDate').value || todayISO());
      });

      document.getElementById('btnCompanyEmailBackup').addEventListener('click', () => {
        sendBackupViaEmail(null);
      });

      document.getElementById('btnDownloadJson').addEventListener('click', () => {
        const payload = JSON.stringify({ settings, entries, exportedAt: new Date().toISOString() }, null, 2);
        const blob = new Blob([payload], { type: 'application/json' });
        const url = URL.createObjectURL(blob);
        const a = document.createElement('a');
        a.href = url;
        a.download = `gate_register_backup_${todayISO()}.json`;
        document.body.appendChild(a);
        a.click();
        document.body.removeChild(a);
        URL.revokeObjectURL(url);
        showToast('Backup file downloaded!');
      });

      document.getElementById('restoreJsonInput').addEventListener('change', function (e) {
        const file = e.target.files[0];
        if (!file) return;
        const reader = new FileReader();
        reader.onload = function (ev) {
          try {
            const data = JSON.parse(ev.target.result);
            if (Array.isArray(data.entries)) entries = data.entries;
            if (data.settings) settings = { ...settings, ...data.settings };
            saveEntries();
            safeSetStorage(SETTINGS_KEY, JSON.stringify(settings));
            applyCompanyHeader();
            populateCompanyForm();
            renderCompanyVehicles();
            renderCompanyDrivers();
            updateCounts();
            renderInsideList();
            renderLogsList();
            renderReport();
            showToast('Backup restored successfully!');
          } catch (err) {
            showToast('Invalid backup file');
          }
        };
        reader.readAsText(file);
        this.value = '';
      });

      document.getElementById('btnExportCsv').addEventListener('click', () => {
        const headers = ['Vehicle No', 'Type', 'Status', 'Party Name', 'Category', 'Material Details', 'Driver Name', 'Mobile', 'Unit', 'IN Reading', 'OUT Reading', 'IN Time', 'OUT Time', 'OUT Note'];
        const rows = entries.map(e => [
          e.vehicleNo, e.vehicleType, e.status, e.partyName, e.category, e.materialDetails,
          e.driverName, e.driverMobile, e.readingUnit, e.inReading ?? '', e.outReading ?? '',
          e.inTime ? new Date(e.inTime).toLocaleString('en-IN') : '',
          e.outTime ? new Date(e.outTime).toLocaleString('en-IN') : '',
          e.outRemark || ''
        ].map(v => `"${String(v || '').replace(/"/g, '""')}"`).join(','));
        const csv = [headers.join(','), ...rows].join('\n');
        const blob = new Blob([csv], { type: 'text/csv;charset=utf-8;' });
        const url = URL.createObjectURL(blob);
        const a = document.createElement('a');
        a.href = url;
        a.download = `gate_vehicle_register_${todayISO()}.csv`;
        document.body.appendChild(a);
        a.click();
        document.body.removeChild(a);
        URL.revokeObjectURL(url);
        showToast('CSV exported!');
      });

      document.getElementById('btnLoadSampleData').addEventListener('click', () => {
        entries = createSampleEntries();
        saveEntries();
        updateCounts();
        renderInsideList();
        renderLogsList();
        renderReport();
        showToast('Demo entries loaded');
      });

      document.getElementById('btnClearAllData').addEventListener('click', () => {
        openConfirm('Clear All Entries?', 'This will permanently delete all saved gate entries on this device.', () => {
          entries = [];
          saveEntries();
          updateCounts();
          renderInsideList();
          renderLogsList();
          renderReport();
          showToast('All entries cleared');
        });
      });

      document.getElementById('btnWaSingleSend').addEventListener('click', async () => {
        const txt = document.getElementById('waSingleText').value;
        const entry = currentWaEntry;
        const photoSrc = entry ? ((entry.status === 'OUT' && entry.outPhoto) ? entry.outPhoto : (entry.inPhoto || entry.outPhoto || '')) : '';

        if (photoSrc && navigator.share) {
          try {
            const res = await fetch(photoSrc);
            const blob = await res.blob();
            const vName = entry ? entry.vehicleNo.replace(/\s+/g, '_') : 'vehicle';
            const file = new File([blob], `${vName}_photo.jpg`, { type: blob.type || 'image/jpeg' });
            if (navigator.canShare && navigator.canShare({ files: [file] })) {
              await navigator.share({
                files: [file],
                text: txt,
                title: `${entry.vehicleNo} Gate Report`
              });
              return;
            }
          } catch (err) {
            if (err && err.name === 'AbortError') return;
          }
        }
        window.open('https://wa.me/?text=' + encodeURIComponent(txt), '_blank');
      });
      document.getElementById('btnWaSingleCopy').addEventListener('click', () => {
        const ta = document.getElementById('waSingleText');
        if (navigator.clipboard && navigator.clipboard.writeText) {
          navigator.clipboard.writeText(ta.value).then(() => showToast('Entry copied for WhatsApp!')).catch(() => {
            ta.select();
            document.execCommand('copy');
            showToast('Entry copied!');
          });
        } else {
          ta.select();
          document.execCommand('copy');
          showToast('Entry copied!');
        }
      });
      document.getElementById('btnWaSingleClose').addEventListener('click', closeSingleWaModal);
      document.getElementById('btnWaSingleCloseX').addEventListener('click', closeSingleWaModal);

      document.getElementById('btnConfirmCancel').addEventListener('click', closeConfirm);
      document.getElementById('btnConfirmOk').addEventListener('click', () => {
        if (confirmCallback) confirmCallback();
        closeConfirm();
      });

      loadState();
      updateCounts();
      updateClocks();
      setInterval(updateClocks, 15000);
    })();
  </script>
</body>
</html>
