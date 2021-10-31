from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import time
from pathlib import Path
from selenium.webdriver.common.by import By

source1 = "https://setec.mk/index.php?route=product/product&path=10066_10067&product_id=50472"
source2 = "https://www.anhoch.com/product/599871427/apple-iphone-12-64gb-black"

# webdriver kurulumu ve onu chrome icin uyarlama
wait_imp = 10
CO = webdriver.ChromeOptions()
CO.add_experimental_option('useAutomationExtension', False)
CO.add_argument('--ignore-certificate-errors')
CO.add_argument('--start-maximized')
wd = webdriver.Chrome(r'C:/Users/Lenovo/Desktop/Desktop/Programlama/chromedriver_win32/chromedriver.exe',options=CO)
print ("*************************************************************************** \n")
print("                     Program baslatiliyor ..... \n")

print ("Setec'e baglaniliyor..")
wd.get(source1)
wd.implicitly_wait(wait_imp)
f_price = wd.find_element(By.XPATH, '/html/body/div[1]/div/div[4]/div[2]/div[2]/div/div[1]/div/div/div/div/div[1]/div/div/div/div[2]/div[1]/div[3]/span')
pr_name = wd.find_element(By.XPATH, '/html/body/div[1]/div/div[3]/div[2]/div[2]/div/div/div/div[2]/h1')
product = pr_name.text
r_price = f_price.text

print (" ---> Fiyat Setec'ten basariyla alindi. \n")
time.sleep(2)

print("Anhoch'a baglaniliyor.")
wd.get(source2)
wd.implicitly_wait(wait_imp)

a_price = wd.find_element(By.XPATH, '//span[@class="nm"]')
raw_p = a_price.text

print (" ---> Fiyat Anhochtan basariyla alindi \n")
time.sleep(2)



# Ciktilarin yazildigi yer
print ("#------------------------------------------------------------------------#")
print ("Price for [{}] on all websites, Prices are in MKD \n".format(product))
print("Price available at Setec is: "+r_price)
print("  Price available at Anhoch is: "+raw_p)


