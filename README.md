# Logik - Laboration 2
## Bankomatmodell
Vi har valt att beskriva den bankomat som vi gjort i programmeringsparadigmkursen.

M = (S, →, L) där

S = {Updates, Login_id, Login_password, Menu, Withdrawal, Balance}

→ = {(Updates, Login_id), (Login_id, Login_password), (Login_id, Updates), 
    (Login_password, Menu), (Login_password, Updates), (Menu, Updates), 
    (Menu, Withdrawal), (Menu, Balance), (Withdrawal, Menu), (Balance, Menu)}

L = {Updates: {}, Login_id: {}, Login_password: {Valid_id}, 
    Menu: {Valid_id, Valid_pwd, Access}, 
    Withdrawal: {Valid_id, Valid_pwd, Access},
    Balance: {Valid_id, Valid_pwd, Access}}
    
## Krav på systemet
Det får inte finnas något state där man har access men det saknas giltigt id eller giltigt lösenord.

M, Updates ⊢ AG ¬((¬Valid_id ⋁ ¬Valid_pwd) ⋀ Access)

Man ska inte heller kunna ha ett giltigt lösenord utan att ha ett giltigt id.

M, Updates ⊢ AG ¬(¬Valid_id ⋀ Valid_pwd)

Man ska inte kunna gå direkt från att ge sitt id till att ha access.

M, Login_id ⊢ AX ¬Access

Man ska inte heller kunna ha ett giltigt lösenord utan att först ha ett giltigt id.

M, Updates ⊢ AG ¬(¬Valid_id ⋀ EX Valid_pwd)
