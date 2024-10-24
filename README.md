- 👋 Hi, I’m @justin123-elec

library ieee;
use ieee.std_logic_1164.all;
entity tb_rq_4 is
end tb_rq_4;
architecture testbench of tb_rq_4 is
  signal clk   : std_logic := '0';
  signal clear : std_logic := '1';
  signal D     : std_logic_vector(3 downto 0) := (others => '0');
  signal Q     : std_logic_vector(3 downto 0);
  component rq_4
    port(
      clk   : in std_logic;
      clear : in std_logic;
      D     : in std_logic_vector(3 downto 0);
      Q     : out std_logic_vector(3 downto 0));
  end component;
begin
  uut: rq_4
    port map(
      clk   => clk,
      clear => clear,
      D     => D,
      Q     => Q  );
  clk_process: process
  begin
    while true loop
      clk <= '0';
      wait for 5 ns;
      clk <= '1';
      wait for 5 ns;
    end loop;
  end process clk_process;
  process
  begin
    clear <= '0';
    wait for 20 ns;
    clear <= '1';
    D <= "0001"; wait for 10 ns;
    D <= "0010"; wait for 10 ns;
    D <= "0100"; wait for 10 ns;
    D <= "1000"; wait for 10 ns;
    clear <= '1';
    D <= "1100"; wait for 10 ns;
    D <= "1010"; wait for 10 ns;
    D <= "1011"; wait for 10 ns;
    D <= "1101"; wait for 10 ns;
    D <= "1110"; wait for 10 ns;
    D <= "1111"; wait for 10 ns;
    wait;
  end process;
end testbench; find the error this vhdl code 
