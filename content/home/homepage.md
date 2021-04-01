---
# A Demo section created with the Blank widget.
# Any elements can be added in the body: https://wowchemy.com/docs/writing-markdown-latex/
# Add more sections by duplicating this file and customizing to your requirements.

widget: blank  # See https://wowchemy.com/docs/page-builder/
headless: true  # This file represents a page section.
weight: 10  # Order that this section will appear.

title: "👋 Donate now to goJewish.eu"
subtitle: "It all starts with you"

design:
  # Choose how many columns the section has. Valid values: 1 or 2.
  columns: '1'
  background:
    # Apply a background color, gradient, or image.
    #   Uncomment (by removing `#`) an option to apply it.
    #   Choose a light or dark text color by setting `text_color_light`.
    #   Any HTML color name or Hex value is valid.
    #color: white
    gradient_start: white
    gradient_end: black
    #image: hello.jpg  # Name of image in `static/media/`.
    image_darken: 0.4
    image_size: cover
    image_position: right
    image_parallax: true
    text_color_light: true
advanced:
  css_style:
  css_class: fullscreen
---
# link
[Donate](https://payment.maksekeskus.ee/pay/1/link.html?shopId=17150094-1cd0-409f-bfc7-5c9b468a1694&amount=100&paymentId=100&locale=et&country=ee)


# button
<form action="https://payment.maksekeskus.ee/pay/1/link.html"><input type="hidden" name="shopId" value="17150094-1cd0-409f-bfc7-5c9b468a1694"><input type="hidden" name="amount" value="100"><input type="hidden" name="paymentId" value="100"><input type="hidden" name="locale" value="et"><input type="hidden" name="country" value="ee"><input type="hidden" name="donate" value="true"><input type="submit" value="Donate 100€"></form>


#form
<script>
	function switchTab() {
		var labels = document.querySelectorAll('#donations_form > label');

		var e = document.getElementsByClassName("project-select")[0]
		var el = e.options[e.selectedIndex];

		var oneTime = el.getAttribute("data-one-time");
		var reccurring = el.getAttribute("data-recurring");

		var visibleLabel = 'position:relative!important;top:0px!important;margin-right:5px!important;margin-bottom:-1px!important;padding:12px 20px!important;font-weight:600!important;font-size:14px!important;line-height:18px!important;height:18px!important;text-align:center!important;border-left-width:1px!important;border-left-style:solid!important;border-left-color:#C6C6C6!important;border-right-width:1px!important;border-right-style:solid!important;border-right-color:#C6C6C6!important;border-top-width:1px!important;border-top-style:solid!important;border-top-color:#C6C6C6!important;border-top-left-radius:10px!important;border-top-right-radius:10px!important;background-color:white!important;background:-moz-linear-gradient(0deg, white 0%, white 90%, #f4ebb9 90%, #f4ebb9 100%)!important;background: -webkit-linear-gradient(0deg, white 0%, white 90%, #f4ebb9 90%, #f4ebb9 100%)!important;background: linear-gradient(0deg, white 0%, white 90%, #f4ebb9 90%, #f4ebb9 100%)!important;float: none!important;box-sizing: content-box!important;display: inline-block!important;';
		var visibleLabelNotActive = 'position:relative!important;top:1px!important;margin-right:5px!important;margin-bottom: 0px!important;padding:12px 20px!important;font-weight:600!important;font-size:14px!important;line-height:14px!important;height:14px!important;text-align:center!important;border-left-width:1px!important;border-left-style:solid!important;border-left-color:#C6C6C6!important;border-right-width:1px!important;border-right-style:solid!important;border-right-color:#C6C6C6!important;border-top-width:1px!important;border-top-style:solid!important;border-top-color:#C6C6C6!important;border-top-left-radius:10px!important;border-top-right-radius:10px!important;background-color:#E3E3E3!important;background-image:none!important;background-repeat:repeat!important;background-position:top left!important;background-attachment:scroll!important;float: none!important;box-sizing: content-box!important;display:inline-block!important';

		if (oneTime != null && reccurring != null) {
			for (var i = 0; i < labels.length; i++) {
				var label = labels[i];
				var tabContent = document.getElementById(label.htmlFor + '_content');
				if (document.getElementById(label.htmlFor).checked) {
					label.style = visibleLabel;
					showElement(tabContent, 'block')
				} else {
					label.style = visibleLabelNotActive;
					hideElement(tabContent)
				}
			}
		} else {
			hideTabs(oneTime, visibleLabel);
		}
	}

	function hideTabs(oneTime, visibleLabel) {
		if (oneTime == null) {
			document.getElementById("mkdf.recurring").style = visibleLabel
			showElement(document.getElementById("donations_tabs_2_content"), 'block')
			hideElement(document.getElementById("mkdf.one.time"))
			hideElement(document.getElementById("donations_tabs_1_content"))
		} else {
			document.getElementById("mkdf.one.time").style = visibleLabel;
			showElement(document.getElementById("donations_tabs_1_content"), 'block')
			hideElement(document.getElementById("mkdf.recurring"))
			hideElement(document.getElementById("donations_tabs_2_content"))
		}
	}

	document.addEventListener("DOMContentLoaded", function () {
		switchTab();
	});

	function hideElement(element) {
		element.style.setProperty('display', 'none', 'important');
	}

	function showElement(element, blockVariation) {
		element.style.setProperty('display', blockVariation, 'important');
	}

	function setAmountBorder(el, checked) {
		if (checked) {
			el.style.setProperty('border', '4px solid #F7D728', 'important');
			el.style.setProperty('padding', '5px 7px', 'important');
		} else {
			el.style.setProperty('border', '1px solid #C6C6C6', 'important');
			el.style.setProperty('padding', '8px 10px', 'important');
		}
	}

	function getAmountInput() {
		return document.getElementById('donations_sum_number');
	}

	function setAmountBorders(ignoreChecked) {
		var labels = document.querySelectorAll('#donationAmounts > .mkdf-form-item-button > label, #donationAmounts > .mkdf-form-item-labeled > label');
		var borderElement;
		for (var i = 0; i < labels.length; i++) {
			var label = borderElement = labels[i];
			var input = document.getElementById(label.htmlFor);
			if (input.id === 'donations_sum_write') {
				borderElement = getAmountInput();
			}
			setAmountBorder(borderElement, input.checked || ignoreChecked);
		}
	}

	function changeDonationAmount() {
		document.getElementById("mkdf.donate.sum.notice").style.setProperty('color', '', 'important');
		setAmountBorders(false);
	}

	function flashAmountBorders(times, on) {
		setAmountBorders(on);
		if (times <= 0 && !on) {
			return;
		}
		setTimeout(function () {
			flashAmountBorders(times - 1, !on);
		}, 300);
	}

	function isValidAmount() {
		var donationsSums = document.getElementsByName('donations_sum');
		var checked = document.querySelector('input[name=\'donations_sum\']:checked');
		var amount = checked && checked.value === 'custom' ? parseFloat(getAmountInput().value) : NaN;
		if (!donationsSums[0].checkValidity() ||
			(checked && checked.value === 'custom' && (isNaN(amount) || amount <= 0))) {
			document.getElementById("mkdf.donate.sum.notice").style.setProperty('color', 'red', 'important');
			if (checked && checked.value === 'custom') {
				checked.checked = false;
			}
			flashAmountBorders(4, true);
			return false;
		}
		return true;
	}

	function setCustomerDataBorders(on) {
		setAmountBorder(document.getElementById('customer_data'), on);
	}

	function flashCustomerDataBorders(times, on) {
		setCustomerDataBorders(on);
		if (times <= 0 && !on) {
			return;
		}
		setTimeout(function () {
			flashCustomerDataBorders(times - 1, !on);
		}, 300);
	}

	function isValidCustomerData(fullName, idCode, email) {
		if (fullName.checkValidity() && idCode.checkValidity() && email.checkValidity()) {
			return true;
		}
		flashCustomerDataBorders(4, true);
		return false;
	}

	function changeBankLink(el) {
		var fullName = document.getElementById('mkdf.donator.full.name');
		var idCode = document.getElementById("mkdf.donator.personCode");
		var email = document.getElementById("mkdf.donator.email");
		if (!isValidAmount() | !isValidCustomerData(fullName, idCode, email)) {
			el.checked = false;
			return;
		}

		changeBankLinkStyle(el);

		var checkedAmount = document.querySelector('input[name=\'donations_sum\']:checked');
		var amount = checkedAmount.value === 'custom' ? getAmountInput().value : checkedAmount.value;

		var gatewayUrl = document.getElementById("mkdf.gateway.url");

		var donationProjectId = getCurrentDonationProjectId();
		var locale = document.getElementById("mkdf.locale");
		var country = document.getElementById("mkdf.country");

		if ((gatewayUrl.checkValidity() && donationProjectId)) {
			var url = getGatewayUrl(gatewayUrl.value, donationProjectId, el.value, "false", amount, fullName.value, idCode.value, email.value, locale.value, country.value);
			console.log(url.toString());
			window.open(url, '_blank');
		} else {
			console.log('Parameters not valid!');
		}
	}

	function changeBankLinkStyle(el) {
		var donationsBanks = document.getElementsByName(el.name);
		for (var i = 0; i < donationsBanks.length; i++) {
			var element = donationsBanks[i];
			var elementToResetStyles = element.nextElementSibling;
			elementToResetStyles.style.setProperty('border', '4px solid #FFF', 'important');
		}

		var elementToApplyStyles = el.nextElementSibling;
		elementToApplyStyles.style.setProperty('background', '#FFC600', 'important');
		elementToApplyStyles.style.setProperty('border', '4px solid #F7D728', 'important');
	}

	function getGatewayUrl(gatewayUrl, donationProjectId, channel, standingOrder, amount, fullName, idCode, email, locale, country) {
		var url = new URL(gatewayUrl + '/donate.html');
		url.searchParams.append('do', donationProjectId);
		url.searchParams.append('ch', channel);
		url.searchParams.append('st', standingOrder);

		url.searchParams.append('am', amount == null ? '' : amount);
		url.searchParams.append('na', fullName == null ? '' : fullName);
		url.searchParams.append('pe', idCode == null ? '' : idCode);
		url.searchParams.append('em', email == null ? '' : email);
		url.searchParams.append('lo', locale == null ? '' : locale);
		url.searchParams.append('co', country == null ? '' : country);

		return url.toString();
	}


	function getCurrentDonationProjectId() {
		var e = document.getElementsByClassName("project-select")[0];
		return e.options[e.selectedIndex].getAttribute("data-project-id");
	}

	function changeBankLinkSo(el) {
		changeBankLinkStyle(el);

		var gatewayUrl = document.getElementById("mkdf.gateway.url");

		var donationProjectId = getCurrentDonationProjectId();
		var locale = document.getElementById("mkdf.locale");
		var country = document.getElementById("mkdf.country");

		if (gatewayUrl.checkValidity() && donationProjectId) {
			var url = getGatewayUrl(gatewayUrl.value, donationProjectId, el.value, "true", null, null, null, null, locale.value, country.value);
			console.log(url.toString());
			window.open(url, '_blank');
		} else {
			console.log('Parameters not valid!');
		}
	}

	function validate(input) {
		var feedback = input.nextElementSibling;
		feedback.style.setProperty('display', (input.checkValidity() ? 'none' : 'inline-block'), 'important');
	}

	function donationSumNeedBeChecked() {
		var checked = null;
		var donationsSums = document.getElementsByName("donations_sum");
		for (var i = 0; i < donationsSums.length; i++) {
			var element = donationsSums[i];
			if (element.checked) {
				checked = element;
				break;
			}
		}
		return !!checked && checked.value === 'custom';
	}

	function syncSelectDropdowns(tab) {
		var isOneTimeTab = tab === 'one-time';
		var e = document.getElementsByClassName("project-select")[isOneTimeTab ? 0 : 1];
		document.getElementsByClassName("project-select")[isOneTimeTab ? 1 : 0][e.selectedIndex].selected = true;
		return e.options[e.selectedIndex];
	}

	function deselectDonationAmounts() {
		var checked = document.querySelector('input[name=\'donations_sum\']:checked');
		if (checked != null) {
			checked.checked = false
			setAmountBorders(false);
		}
	}

	function selectDropdownChange(tab) {
		var donationsSumPrefix = "donations_sum_";
		deselectDonationAmounts();
		var el = syncSelectDropdowns(tab);

		for (var i = 0; i < 3; i++) {
			var amount = el.getAttribute("data-amount" + i);
			var amountDiv = document.getElementById(donationsSumPrefix + i + "-div");
			if (amount != null) {
				showElement(amountDiv, 'inline-block');
				document.getElementById(donationsSumPrefix + i).setAttribute("value", amount);
				document.getElementById(donationsSumPrefix + i + "-span").textContent = amount;
			} else {
				hideElement(amountDiv);
			}
		}

		var chooseCustomAmount = el.getAttribute("data-custom-amount");
		var customAmountBlock = document.getElementById("custom-amount-block");
		if (chooseCustomAmount != null) {
			showElement(customAmountBlock, 'inline-block')
		} else {
			hideElement(customAmountBlock)
		}

		switchTab()
	}


</script> 
<div id="donations_form" class="mkdf-form" style="position:relative!important;font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display: inline-block!important;"> 
 <input id="donations_tabs_1" type="radio" name="donations_tabs" value="0" style="font-size:14px!important;font-family:'Titillium Web', Arial, Helvetica, sans-serif!important;display:none!important;" onclick="switchTab()" checked="true"> <label for="donations_tabs_1" id="mkdf.one.time" style="position:relative!important;top:1px!important;margin-right:5px!important;margin-bottom: 0px!important;padding-top:12px!important;padding-bottom:12px!important;padding-right:20px!important;padding-left:20px!important;font-weight:600!important;font-size:14px!important;line-height:14px!important;height:14px!important;text-align:center!important;border-left-width:1px!important;border-left-style:solid!important;border-left-color:#C6C6C6!important;border-right-width:1px!important;border-right-style:solid!important;border-right-color:#C6C6C6!important;border-top-width:1px!important;border-top-style:solid!important;border-top-color:#C6C6C6!important;border-top-left-radius:10px!important;border-top-right-radius:10px!important;background-color:#E3E3E3!important;background-image:none!important;background-repeat:repeat!important;background-position:top left!important;background-attachment:scroll!important;float: none!important;box-sizing: content-box!important;display:inline-block!important;">Ühekordne annetus</label> 
 <input id="donations_tabs_2" type="radio" name="donations_tabs" value="1" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onclick="switchTab()"> <label for="donations_tabs_2" id="mkdf.recurring" style="position:relative!important;top:1px!important;margin-right:5px!important;margin-bottom: 0px!important;padding-top:12px!important;padding-bottom:12px!important;padding-right:20px!important;padding-left:20px!important;font-weight:600!important;font-size:14px!important;line-height:14px!important;height:14px!important;text-align:center!important;border-left-width:1px!important;border-left-style:solid!important;border-left-color:#C6C6C6!important;border-right-width:1px!important;border-right-style:solid!important;border-right-color:#C6C6C6!important;border-top-width:1px!important;border-top-style:solid!important;border-top-color:#C6C6C6!important;border-top-left-radius:10px!important;border-top-right-radius:10px!important;background-color:#E3E3E3!important;background-image:none!important;background-repeat:repeat!important;background-position:top left!important;background-attachment:scroll!important;float: none!important;box-sizing: content-box!important;display:inline-block!important;">Püsiannetus</label> 
 <input id="mkdf.gateway.url" name="mkdf.gateway.url" type="hidden" value="https://payment.maksekeskus.ee"> 
 <input id="mkdf.project.id" type="hidden" name="mkdf.project.id" value="dcc4e097-8bc8-4682-b61e-606519348e27"> 
 <input id="mkdf.locale" type="hidden" name="mkdf.locale" value="et"> 
 <input id="mkdf.country" type="hidden" name="mkdf.country" value="EE"> 
 <div class="mkdf-containter" style="border-width:1px!important;border-style:solid!important;border-color:#C6C6C6!important;border-radius:15px!important;border-top-left-radius:0!important;overflow:hidden!important;box-sizing: content-box!important;"> 
  <div id="donations_tabs_1_content" class="donations_tabs_content"> 
   <div id="donations_content_1" class="mkdf-content" style="padding-top:15px!important;padding-bottom:15px!important;padding-right:15px!important;padding-left:15px!important;border-bottom-width:6px!important;border-bottom-style:solid!important;border-bottom-color:#F4EBB9!important;box-sizing: content-box!important;"> 
    <div class="mkdf-form-items" style="padding-top:25px!important;"> 
     <div class="mkdf-label mkdf.project" style="padding-bottom:10px!important;font-weight:600!important;">
      Toetatav projekt
     </div> <select class="project-select" onchange="selectDropdownChange('one-time')" style="height: 100%;font-family:Arial, Helvetica, sans-serif!important;display:inline-block!important;width:100%!important;min-width:300px!important;max-width:480px!important;font-size:18px!important;line-height:25px!important;font-weight:300!important;color:#444!important;padding-top:8px!important;padding-bottom:8px!important;padding-right:40px!important;padding-left:8px!important;box-sizing:border-box!important;margin-top:0!important;margin-bottom:0!important;margin-right:0!important;margin-left:0!important;border-width:1px!important;border-style:solid!important;border-color:#C6C6C6!important;border-radius:10px!important;-moz-appearance:none!important;-webkit-appearance:none!important;appearance:none!important;background-color:#FFF!important;background-image:url('data:image/svg+xml,%3Csvg id=\'Layer_1\' data-name=\'Layer 1\' xmlns=\'http://www.w3.org/2000/svg\' viewBox=\'0 0 20 8.84\'%3E%3Cdefs%3E%3Cstyle%3E.cls-1%7Bfill:%235c5b5b!important;%7D%3C/style%3E%3C/defs%3E%3Cpath class=\'cls-1\' d=\'M8.84,9.84,0,1H3L9.43,7.62h.13L16.87,1H20L10.05,9.84Z\' transform=\'translate(0.04 -1)\'/%3E%3C/svg%3E')!important;background-repeat:no-repeat, repeat!important;background-position:right 0.5em top 50%, 0 0!important;background-size:0.75em auto, 100%!important;"> <option data-amount0="20.00" data-amount1="50.00" data-amount2="100.00" data-one-time data-recurring data-custom-amount data-project-id="dcc4e097-8bc8-4682-b61e-606519348e27" selected="true">goJewish.eu</option></select> 
    </div> 
    <div class="mkdf-form-items" style="padding-top:25px!important;"> 
     <div id="mkdf.donate.money" class="mkdf-label" style="padding-bottom:10px!important;font-weight:600!important;">
      Annetan raha
     </div> 
     <div id="mkdf.donate.sum.notice" class="mkdf-description" style="padding-bottom:8px!important;font-weight:400!important;">
      Vali annetuse summa või kirjuta sobiv summa lahtrisse
     </div> 
     <div id="donationAmounts" class="mkdf-form-items-horizontal">     
      <div class="mkdf-form-item mkdf-form-item-button" style="display:inline-block!important" id="donations_sum_0-div"> 
       <input id="donations_sum_0" type="radio" required name="donations_sum" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeDonationAmount(this)" value="20.00"> <label for="donations_sum_0" style="display:inline-block!important;border-width:1px!important;border-style:solid!important;border-color:#C6C6C6!important;border-radius:10px!important;padding-top:8px!important;padding-bottom:8px!important;padding-right:10px!important;padding-left:10px!important;font-size:18px!important;line-height:23px!important;height:25px!important;float: none!important;box-sizing: content-box!important;cursor: pointer!important;"><span id="donations_sum_0-span">20.00</span> €</label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-button" style="display:inline-block!important" id="donations_sum_1-div"> 
       <input id="donations_sum_1" type="radio" required name="donations_sum" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeDonationAmount(this)" value="50.00"> <label for="donations_sum_1" style="display:inline-block!important;border-width:1px!important;border-style:solid!important;border-color:#C6C6C6!important;border-radius:10px!important;padding-top:8px!important;padding-bottom:8px!important;padding-right:10px!important;padding-left:10px!important;font-size:18px!important;line-height:23px!important;height:25px!important;float: none!important;box-sizing: content-box!important;cursor: pointer!important;"><span id="donations_sum_1-span">50.00</span> €</label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-button" style="display:inline-block!important" id="donations_sum_2-div"> 
       <input id="donations_sum_2" type="radio" required name="donations_sum" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeDonationAmount(this)" value="100.00"> <label for="donations_sum_2" style="display:inline-block!important;border-width:1px!important;border-style:solid!important;border-color:#C6C6C6!important;border-radius:10px!important;padding-top:8px!important;padding-bottom:8px!important;padding-right:10px!important;padding-left:10px!important;font-size:18px!important;line-height:23px!important;height:25px!important;float: none!important;box-sizing: content-box!important;cursor: pointer!important;"><span id="donations_sum_2-span">100.00</span> €</label> 
      </div>
      <div id="custom-amount-block" class="mkdf-form-item mkdf-form-item-labeled" style="padding-left:15px!important;display:inline-block!important;"> 
       <input id="donations_sum_write" type="radio" value="custom" required name="donations_sum" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeDonationAmount(this)"> <label for="donations_sum_write" onclick="document.getElementById('donations_sum_number').focus();" style="height: 25px!important;float: none!important;box-sizing: content-box!important;"> <span id="mkdf.donate.sum.write">või kirjuta sobiv summa:</span> <input id="donations_sum_number" onclick="document.getElementById('donations_sum_write').click()" type="text" name="donations_sum_number" style="font-family:Arial, Helvetica, sans-serif!important;display:inline-block!important;border-width:1px!important;border-style:solid!important;border-color:#C6C6C6!important;border-radius:10px!important;padding-top:8px!important;padding-bottom:8px!important;padding-right:12px!important;padding-left:12px!important;position:relative!important;max-width:100px!important;font-size:18px!important;line-height:23px!important;height:23px!important;box-sizing:content-box!important;" required> </label> 
      </div>
     </div> 
    </div> 
    <div class="mkdf-form-items" style="padding-top:25px!important;"> 
     <div id="mkdf.donator.data" class="mkdf-label" style="padding-bottom:10px!important;font-weight:600!important;">
      Minu andmed
     </div> 
     <div id="customer_data" class="mkdf-form-items-block" style="display:inline-block!important;border-width:1px!important;border-style:solid!important;border-color:#C6C6C6!important;border-radius:10px!important;padding-top:0!important;padding-bottom:0!important;padding-right:10px!important;padding-left:10px!important;box-sizing: content-box!important;"> 
      <div class="mkdf-form-item"> 
       <input id="mkdf.donator.full.name" type="text" onfocusout="validate(this);" pattern="^\s*[^\s]+\s+[^\s]+.*$" name="mkdf.donator.full.name" placeholder="Nimi" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:inline-block!important;border-style:solid!important;border-color:#C6C6C6!important;width:200px!important;max-width:270px!important;border-width:0!important;border-bottom-width:1px!important;border-bottom-style:solid!important;border-bottom-color:#C6C6C6!important;border-radius:0!important;padding-top:6px!important;padding-bottom:6px!important;padding-right:0!important;padding-left:0!important;outline:none!important;box-sizing: content-box!important;"> 
       <div id="mkdf.donator.full.name.invalid" class="invalid-feedback" style="color:red!important;display:none!important;">
        Palun kontrollige oma ees- ja perekonnanime
       </div> 
      </div> 
      <div class="mkdf-form-item"> 
       <input id="mkdf.donator.personCode" type="text" name="mkdf.donator.personCode" placeholder="Isikukood" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:inline-block!important;border-style:solid!important;border-color:#C6C6C6!important;width:200px!important;max-width:270px!important;border-width:0!important;border-bottom-width:1px!important;border-bottom-style:solid!important;border-bottom-color:#C6C6C6!important;border-radius:0!important;padding-top:6px!important;padding-bottom:6px!important;padding-right:0!important;padding-left:0!important;outline:none!important;box-sizing: content-box!important;"> 
      </div> 
      <div class="mkdf-form-item"> 
       <input id="mkdf.donator.email" type="email" onfocusout="validate(this);" name="mkdf.donator.email" placeholder="E-mail" style="font-size:14px!important;font-family:'Titillium Web', Arial, Helvetica, sans-serif!important;display:inline-block!important;border-style:solid!important;border-color:#C6C6C6!important;width:200px!important;max-width:270px!important;border-width:0!important;border-bottom-width:0px!important;border-bottom-style:solid!important;border-bottom-color:#C6C6C6!important;border-radius:0!important;padding-top:6px!important;padding-bottom:6px!important;padding-right:0!important;padding-left:0!important;outline:none!important;box-sizing: content-box!important;"> 
       <div id="mkdf.donator.email.invalid" class="invalid-feedback" style="color:red!important;display:none!important;">
        Palun kontrollige e-mail addressi
       </div> 
      </div> 
     </div> 
    </div> 
    <div class="mkdf-form-items" style="padding-top:25px!important;"> 
     <div class="mkdf-label mkdf.payment" style="padding-bottom:10px!important;font-weight:600!important;">
      Vormistamine
     </div> 
     <div class="mkdf-description mkdf.payment.description" style="padding-bottom:8px!important;font-weight:400!important;">
      Vormista annetus valides eelistatud panga
     </div> 
     <div class="mkdf-form-items-horizontal mkdf-form-items-banklinks" style="margin-right:-5px!important;margin-left:-5px!important;">  
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="EE_SWED" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="EE_SWED"> <label for="EE_SWED" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/swedbank.png" alt="EE_SWED" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="EE_SEB" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="EE_SEB"> <label for="EE_SEB" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/seb.png" alt="EE_SEB" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="EE_LHV" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="EE_LHV"> <label for="EE_LHV" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/lhv.png" alt="EE_LHV" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="EE_NORDEA" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="EE_NORDEA"> <label for="EE_NORDEA" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/luminor.png" alt="EE_NORDEA" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="EE_KREDIIDI" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="EE_KREDIIDI"> <label for="EE_KREDIIDI" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/coop.png" alt="EE_KREDIIDI" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="EE_POCOPAY" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="EE_POCOPAY"> <label for="EE_POCOPAY" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/pocopay.png" alt="EE_POCOPAY" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="LV_SWED_OB" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="LV_SWED_OB"> <label for="LV_SWED_OB" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/swedbank.png" alt="LV_SWED_OB" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="LV_SEB_OB" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="LV_SEB_OB"> <label for="LV_SEB_OB" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/seb.png" alt="LV_SEB_OB" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="LT_SWED_OB" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="LT_SWED_OB"> <label for="LT_SWED_OB" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/swedbank.png" alt="LT_SWED_OB" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="LT_SEB_OB" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="LT_SEB_OB"> <label for="LT_SEB_OB" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/seb.png" alt="LT_SEB_OB" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="FI_PAYTRAIL_NORDEA" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="FI_PAYTRAIL_NORDEA"> <label for="FI_PAYTRAIL_NORDEA" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/nordeafi.png" alt="FI_PAYTRAIL_NORDEA" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="FI_PAYTRAIL_DANSKE" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="FI_PAYTRAIL_DANSKE"> <label for="FI_PAYTRAIL_DANSKE" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/danske.png" alt="FI_PAYTRAIL_DANSKE" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="FI_PAYTRAIL_POHJOLA" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="FI_PAYTRAIL_POHJOLA"> <label for="FI_PAYTRAIL_POHJOLA" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/pohjola.png" alt="FI_PAYTRAIL_POHJOLA" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="FI_PAYTRAIL_ALANDSBANKEN" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="FI_PAYTRAIL_ALANDSBANKEN"> <label for="FI_PAYTRAIL_ALANDSBANKEN" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/alandsbanken.png" alt="FI_PAYTRAIL_ALANDSBANKEN" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="FI_PAYTRAIL_HANDELSBANKEN" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="FI_PAYTRAIL_HANDELSBANKEN"> <label for="FI_PAYTRAIL_HANDELSBANKEN" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/handelsbanken.png" alt="FI_PAYTRAIL_HANDELSBANKEN" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="FI_PAYTRAIL_SPANKKI" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="FI_PAYTRAIL_SPANKKI"> <label for="FI_PAYTRAIL_SPANKKI" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/spankki.png" alt="FI_PAYTRAIL_SPANKKI" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="FI_PAYTRAIL_SAASTOPANKKI" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="FI_PAYTRAIL_SAASTOPANKKI"> <label for="FI_PAYTRAIL_SAASTOPANKKI" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/omasaastopankki.png" alt="FI_PAYTRAIL_SAASTOPANKKI" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="FI_PAYTRAIL_REAL_SAASTOP" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="FI_PAYTRAIL_REAL_SAASTOP"> <label for="FI_PAYTRAIL_REAL_SAASTOP" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/saastopankki.png" alt="FI_PAYTRAIL_REAL_SAASTOP" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="FI_PAYTRAIL_AKTIA" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="FI_PAYTRAIL_AKTIA"> <label for="FI_PAYTRAIL_AKTIA" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/aktia.png" alt="FI_PAYTRAIL_AKTIA" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="FI_PAYTRAIL_POP" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="FI_PAYTRAIL_POP"> <label for="FI_PAYTRAIL_POP" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/poppankki.png" alt="FI_PAYTRAIL_POP" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="LV_LUMINOR_OB" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="LV_LUMINOR_OB"> <label for="LV_LUMINOR_OB" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/luminor.png" alt="LV_LUMINOR_OB" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="LT_LUMINOR_OB" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="LT_LUMINOR_OB"> <label for="LT_LUMINOR_OB" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/luminor.png" alt="LT_LUMINOR_OB" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="LT_SIAULIU_OB" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="LT_SIAULIU_OB"> <label for="LT_SIAULIU_OB" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/siauliu.png" alt="LT_SIAULIU_OB" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="VISA-EVERYPAY" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="EVERYPAY"> <label for="VISA-EVERYPAY" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/visa.png" alt="EVERYPAY" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image banklink" style="display:inline-block!important;"> 
       <input id="MASTERCARD-EVERYPAY" type="radio" name="donations_bank" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" onchange="changeBankLink(this)" value="EVERYPAY"> <label for="MASTERCARD-EVERYPAY" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/mastercard.png" alt="EVERYPAY" style="display:block!important;max-width:90px!important;"></label> 
      </div>
     </div> 
    </div> 
    <div class="mkdf-powered" style="padding-top:16px!important;text-align:center!important;font-size:11px!important;color:#404040!important;"> <span class="mkdf.powered.by" style="display:inline-block!important;line-height:22px!important;height:22px!important;max-width:200px!important;padding-top:0!important;padding-bottom:0!important;padding-right:6px!important;padding-left:6px!important;vertical-align:middle!important;">Annetust vahendab</span> <span style="display:inline-block!important;line-height:22px!important;height:22px!important;max-width:110px!important;padding-top:0!important;padding-bottom:0!important;padding-right:6px!important;padding-left:6px!important;vertical-align:middle!important;"> <img class="mkdf.powered.by.logo" style="display:block!important;width:86px!important;height:20px!important;" src="https://static.maksekeskus.ee/img/makecommerce-double-logo.png"> </span> 
    </div> 
   </div> 
  </div> 
  <div id="donations_tabs_2_content" class="donations_tabs_content"> 
   <div id="donations_content_2" class="mkdf-content" style="padding:15px!important;border-bottom-width:6px!important;border-bottom-style:solid!important;border-bottom-color:#F4EBB9!important;box-sizing: content-box!important;"> 
    <div class="mkdf-form-items" style="padding-top:25px!important;"> 
     <div class="mkdf-label mkdf.project" style="padding-bottom:10px!important;font-weight:600!important;">
      Toetatav projekt
     </div> <select class="project-select" onchange="selectDropdownChange('recurring')" style="height: 100%;font-family:Arial, Helvetica, sans-serif!important;display:inline-block!important;width:100%!important;min-width:300px!important;max-width:480px!important;font-size:18px!important;line-height:25px!important;font-weight:300!important;color:#444!important;padding-top:8px!important;padding-bottom:8px!important;padding-right:40px!important;padding-left:8px!important;box-sizing:border-box!important;margin-top:0!important;margin-bottom:0!important;margin-right:0!important;margin-left:0!important;border-width:1px!important;border-style:solid!important;border-color:#C6C6C6!important;border-radius:10px!important;-moz-appearance:none!important;-webkit-appearance:none!important;appearance:none!important;background-color:#FFF!important;background-image:url('data:image/svg+xml,%3Csvg id=\'Layer_1\' data-name=\'Layer 1\' xmlns=\'http://www.w3.org/2000/svg\' viewBox=\'0 0 20 8.84\'%3E%3Cdefs%3E%3Cstyle%3E.cls-1%7Bfill:%235c5b5b!important;%7D%3C/style%3E%3C/defs%3E%3Cpath class=\'cls-1\' d=\'M8.84,9.84,0,1H3L9.43,7.62h.13L16.87,1H20L10.05,9.84Z\' transform=\'translate(0.04 -1)\'/%3E%3C/svg%3E')!important;background-repeat:no-repeat, repeat!important;background-position:right 0.5em top 50%, 0 0!important;background-size:0.75em auto, 100%!important;"> <option data-amount0="20.00" data-amount1="50.00" data-amount2="100.00" data-one-time data-recurring data-custom-amount data-project-id="dcc4e097-8bc8-4682-b61e-606519348e27" selected="true">goJewish.eu</option></select> 
    </div> 
    <div class="mkdf-form-items" style="padding-top:25px!important;"> 
     <div class="mkdf-label mkdf.payment" style="padding-bottom:10px!important;font-weight:600!important;">
      Vormistamine
     </div> 
     <div class="mkdf-description mkdf.payment.description" style="padding-bottom:8px!important;font-weight:400!important;">
      Vormista annetus valides eelistatud panga
     </div> 
     <div class="mkdf-form-items-horizontal mkdf-form-items-banklinks" style="margin-right:-5px!important;margin-left:-5px!important;">  
      <div class="mkdf-form-item mkdf-form-item-image so-banklink" style="display:inline-block!important;"> 
       <input id="so-EE_SWED" type="radio" name="donations_bank_so" onchange="changeBankLinkSo(this);" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" value="EE_SWED"> <label for="so-EE_SWED" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/swedbank.png" alt="EE_SWED" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image so-banklink" style="display:inline-block!important;"> 
       <input id="so-EE_SEB" type="radio" name="donations_bank_so" onchange="changeBankLinkSo(this);" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" value="EE_SEB"> <label for="so-EE_SEB" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/seb.png" alt="EE_SEB" style="display:block!important;max-width:90px!important;"></label> 
      </div>
      <div class="mkdf-form-item mkdf-form-item-image so-banklink" style="display:inline-block!important;"> 
       <input id="so-EE_LHV" type="radio" name="donations_bank_so" onchange="changeBankLinkSo(this);" style="font-size:14px!important;font-family:Arial, Helvetica, sans-serif!important;display:none!important;" value="EE_LHV"> <label for="so-EE_LHV" style="display:inline-block!important;border-width:4px!important;border-style:solid!important;border-color:#FFF!important;padding-bottom:0!important;box-sizing: content-box!important;"><img src="https://static.maksekeskus.ee/img/channel/lnd/lhv.png" alt="EE_LHV" style="display:block!important;max-width:90px!important;"></label> 
      </div>
     </div> 
    </div> 
    <div class="mkdf-powered" style="padding-top:16px!important;text-align:center!important;font-size:11px!important;color:#404040!important;"> <span class="mkdf.powered.by" style="display:inline-block!important;line-height:22px!important;height:22px!important;max-width:200px!important;padding-top:0!important;padding-bottom:0!important;padding-right:6px!important;padding-left:6px!important;vertical-align:middle!important;">Annetust vahendab</span> <span style="display:inline-block!important;line-height:22px!important;height:22px!important;max-width:110px!important;padding-top:0!important;padding-bottom:0!important;padding-right:6px!important;padding-left:6px!important;vertical-align:middle!important;"> <img class="mkdf.powered.by.logo" style="display:block!important;width:86px!important;height:20px!important;" src="https://static.maksekeskus.ee/img/makecommerce-double-logo.png"> </span> 
    </div> 
   </div> 
  </div> 
 </div> 
</div>
							