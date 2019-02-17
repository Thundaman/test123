----------------------------------------------------------------------------------
-- Company: 
-- Engineer: 
-- 
-- Create Date: 02/11/2019 09:49:29 AM
-- Design Name: 
-- Module Name: unkown_top - Behavioral
-- Project Name: 
-- Target Devices: 
-- Tool Versions: 
-- Description: 
-- 
-- Dependencies: 
-- 
-- Revision:
-- Revision 0.01 - File Created
-- Additional Comments:
-- 
----------------------------------------------------------------------------------


library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

-- Uncomment the following library declaration if using
-- arithmetic functions with Signed or Unsigned values
use IEEE.NUMERIC_STD.ALL;

-- Uncomment the following library declaration if instantiating
-- any Xilinx leaf cells in this code.
--library UNISIM;
--use UNISIM.VComponents.all;

entity unknown_top is
    Port ( xin : in STD_LOGIC_VECTOR (3 downto 0);
           yin : in STD_LOGIC_VECTOR (3 downto 0);
           pout : out STD_LOGIC_VECTOR (7 downto 0));
end unknown_top;

architecture Behavioral of unknown_top is

component fa is
    Port ( a : in STD_LOGIC;
           b : in STD_LOGIC;
           cin : in STD_LOGIC;
           sum : out STD_LOGIC;
           cout : out STD_LOGIC);
end component fa;

component ha is
    Port ( a : in STD_LOGIC;
           b : in STD_LOGIC;
           sum : out STD_LOGIC;
           cout : out STD_LOGIC);
end component ha;
signal sig_p0, sig_p1, sig_p2, sig_p3, sig_p4, sig_p5,sig_p6, sig_p7: std_logic;
signal sig1, sig2, sig3: std_logic;
signal and10, and11, and12, and13, and20, and21, and22, and23: std_logic;
signal and000, and00, and01, and02, and03, and30, and31, and32, and33: std_logic;
signal and40, and41, and42, and43: std_logic;
signal c10, c11, c12, c13, c20, c21, c22, c23, c30, c31, c32, c33: std_logic;
signal s10, s11, s12, s13, s20, s21, s22, s23, s30, s31, s32, s33: std_logic;

begin

-- p0
sig_p0 <= xin(0) and yin(0);
pout(0) <= sig_p0;

-- p1
and00 <= xin(1) and yin(0);
and10 <= xin(0) and yin(1);
u00: ha port map(a => and10, b => and00, sum => s10, cout => c10);
pout(1) <= s10;

--MAYBE SOMETHING MISSING??

--p2
and01 <= xin(2) and yin(0);
and11 <= xin(1) and yin(1);
u01: fa port map(a => and11, b => and01, cin => c10, sum => s11, cout => c11);
and30 <= xin(0) and yin(2);
u10: ha port map(a => and30, b => s11, sum => s20, cout => c20);
pout(2) <= s20;


--p3

and12 <= xin(2) and yin(1);
and02 <= xin(3) and yin(0);
u02: fa port map(a => and12, b => and02, cin => c11, sum => s12, cout => c12);
and31 <= xin(1) and yin(2);
u11: fa port map(a => and31, b => s12, cin => c20, sum => s21, cout => c21);
and40 <= xin(0) and yin(3);
u20: ha port map(a => and40, b => s21, sum => s30, cout => c30);
pout(3) <= s30;


--p4
and13 <= xin(3) and yin(1);
u03: ha port map(a => and13, b=> c12, sum => s13, cout => c13);
and32 <= xin(2) and yin(2);
u12: fa port map(a => and32, b => s13, cin => c21, sum => s22, cout => c22);
and41 <= xin(1) and yin(3);
u21: fa port map(a => and41, b => s22, cin => c30, sum => s31, cout => c31);
pout(4) <= s31;


--p5
and33 <= xin(3) and yin(2);
u13: fa port map(a => and33, b => c13, cin => c22, sum => s23, cout => c23);
and42 <= xin(2) and yin(3);
u22: fa port map(a => and42, b => s23, cin => c31, sum => s32, cout => c32);
pout(5) <= s32;

--p6
and43 <= xin(3) and yin(3);
u23: fa port map(a => and43, b => c23, cin => c32, sum => s33, cout => c33);
pout(6) <= s33;

--p7
pout(7) <= c33;

--u03: ha port map(a =>a_sig, b=>b_sig, cin=>cin_sig, sum =>sum_sig, cout =>cout_sig);

end Behavioral;
