# 
##
M = (S, →, L) där

S = {Updates, Login_id, Login_password, Menu, Withdrawal, Balance}

→  {(Updates, Login_id), (Login_id, Login_password), (Login_id, Updates), 
    (Login_password, Menu), (Login_password, Updates), (Menu, Updates), 
    (Menu, Withdrawal), (Menu, Balance), (Withdrawal, Menu), (Balance, Menu)}

L = {Updates: {}, Login_id: {Accepts_input}, Login_password: {Valid_id, Accepts_input}, 
    Menu: {Valid_id, Valid_pwd, Accepts_input, Access}, 
    Withdrawal: {Valid_id, Valid_pwd, Accepts_input, Access},
    Balance: {Valid_id, Valid_pwd, Accepts_input, Access}}
    
# Krav på systemet
M, Updates ⊢ AG ¬((¬Valid_id ⋁ ¬Valid_pwd) ⋀ Access)
M, Updates ⊢ AG ¬(¬Valid_id ⋀ Valid_pwd)
M, Login_id ⊢ AX ¬Access
