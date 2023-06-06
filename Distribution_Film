architecture archi of distributeur is
    -- Déclaration des types et signaux internes
    type state_type is (Zero, Un, Deux, Trois, Quatre, Cinq, Six);
    signal current_state, next_state : state_type;
    signal total_euros : integer range 0 to 6 := 0;

begin
    -- Processus de transition d'état
    process (clk)
    begin
        if rising_edge(clk) then
            current_state <= next_state;
        end if;
    end process;

    -- Processus de calcul de l'état suivant en fonction de l'état courant et des entrées
    process (current_state, un_Eu, deux_Eu)
    begin
        case current_state is
            when Zero =>
                if un_Eu = '1' then
                    next_state <= Un;
                elsif deux_Eu = '1' then
                    next_state <= Deux;
                else
                    next_state <= Zero;
                end if;
                
            when Un =>
                if un_Eu = '1' then
                    next_state <= Deux;
                elsif deux_Eu = '1' then
                    next_state <= Trois;
                else
                    next_state <= Un;
                end if;
                
            when Deux =>
                if un_Eu = '1' then
                    next_state <= Trois;
                elsif deux_Eu = '1' then
                    next_state <= Quatre;
                else
                    next_state <= Deux;
                end if;
                
            when Trois =>
                if un_Eu = '1' then
                    next_state <= Quatre;
                elsif deux_Eu = '1' then
                    next_state <= Cinq;
                else
                    next_state <= Trois;
                end if;
                
            when Quatre =>
                if un_Eu = '1' then
                    next_state <= Cinq;
                elsif deux_Eu = '1' then
                    next_state <= Six;
                else
                    next_state <= Quatre;
                end if;
                
            when Cinq =>
                if un_Eu = '1' then
                    next_state <= Un;
                elsif deux_Eu = '1' then
                    next_state <= Deux;
                else
                    next_state <= Cinq;
                end if;
                
            when Six =>
                if un_Eu = '1' then
                    next_state <= Un;
                elsif deux_Eu = '1' then
                    next_state <= Deux;
                else
                    next_state <= Six;
                end if;
                
        end case;
    end process;

    -- Processus de sortie en fonction de l'état courant
    process (current_state)
    begin
        case current_state is
            when Cinq =>
                film <= '1';
                monnaie <= '0';
                
            when Six =>
                film <= '1';
                monnaie <= '1';
                
            else
                film <= '0';
                monnaie <= '0';
        end case;
    end process;

end archi
