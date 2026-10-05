# seleniumexercise
## 1. Search Actor Surya
```
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()

driver.get("https://www.google.com/")

input("If CAPTCHA appears, complete it manually, then press Enter...")

search = driver.find_element(By.NAME, "q")

search.send_keys("actor surya")

print("Placeholder:", search.get_attribute("placeholder"))
print("Enabled:", search.is_enabled())
print("Displayed:", search.is_displayed())

search.submit()

input("Search completed. Press Enter to close...")

driver.quit()

```
<img width="1917" height="1138" alt="surya" src="https://github.com/user-attachments/assets/1122f6e0-904d-4701-8d9a-b63854cef249" />

## 2. Go to products page in Saucedemo
```
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()

driver.get("https://www.saucedemo.com/")

username = driver.find_element(By.ID, "user-name")
password = driver.find_element(By.NAME, "password")
login = driver.find_element(By.ID, "login-button")

username.send_keys("standard_user")
password.send_keys("secret_sauce")

print(username.get_attribute("placeholder"))
print(login.is_enabled())
print(username.is_displayed())

login.click()

cart = driver.find_element(By.ID, "add-to-cart-sauce-labs-backpack")
cart.click()

trolly=driver.find_element(By.CLASS_NAME, "shopping_cart_link")
trolly.click()

checkout=driver.find_element(By.CLASS_NAME, "btn btn_action btn_medium checkout_button")
checkout.click()

input("Press Enter to close the browser...")

driver.quit()
```
<img width="1917" height="1140" alt="products" src="https://github.com/user-attachments/assets/3b19fa21-7183-4cbd-af35-f5b24ecddb0f" />

## 3. Flipkart Login With Mobile Number
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

driver = webdriver.Chrome()

driver.get("https://www.flipkart.com/")

wait = WebDriverWait(driver, 20)

# Find mobile number field
number = wait.until(
    EC.visibility_of_element_located(
        (By.CLASS_NAME, "jwCbxy")
    )
)

# Enter mobile number
number.send_keys("7736659787")

print("Placeholder:", number.get_attribute("placeholder"))
print("Displayed:", number.is_displayed())

# Find Continue button
cont = wait.until(
    EC.element_to_be_clickable(
        (By.CSS_SELECTOR, ".xqOMQN.FFO0ui")
    )
)

print("Continue enabled:", cont.is_enabled())

# Click Continue
cont.click()

print("Waiting for OTP...")

# Enter OTP manually
input("Enter the OTP manually in Flipkart, then press Enter here...")

# Find Verify button using all 4 classes
verify = wait.until(
    EC.element_to_be_clickable(
        (By.CSS_SELECTOR, ".xqOMQN.Zu_V0Z.FFO0ui.B_SLby")
    )
)

print("Verify button found!")

# Click Verify
verify.click()

print("Verify button clicked!")

# Wait for Flipkart homepage
wait.until(
    EC.visibility_of_element_located(
        (By.NAME, "q")
    )
)

print("Homepage loaded successfully!")
print("Current URL:", driver.current_url)

# Keep browser open
input("Press Enter to close the browser...")

driver.quit()
```
<img width="1917" height="1136" alt="flipkart" src="https://github.com/user-attachments/assets/254d5078-fee5-4672-bada-f1425f6d5c8c" />

