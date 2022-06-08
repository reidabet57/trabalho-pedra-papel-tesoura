# trabalho-pedra-papel-tesoura

import java.util.Random;
import java.util.Scanner;

public class Main {
 
	static Scanner console = new Scanner (System.in);
	static Random sorteador = new Random();

	static final int[][] REGRAS_DO_JOGO = {
			{ 0, -1, 1, 1, -1},
			{ 1, 0, -1, -1, 1},
			{-1, 1, 0, 1, -1 },
			{-1, 1, -1,0 ,1  },
			{ 1, -1, 1, -1,0 }
					
	};
    
	static final String[] opcoes = {"Pedra","Papel","Tesoura","Lagarto","Spock"};
	
	static final byte GANHOU =  1;
	static final byte EMPATOU = 0;
	static final byte PERDEU = -1;
	
		
	static int obterOpcaoComputador() {	
	return sorteador.nextInt(REGRAS_DO_JOGO.length);
					
	}// Fim do método obterOpcaoComputador();
	
	static int lerOpcaoUsuario() {
	
		System.out.println("[0] Pedra");
		System.out.println("[1] Papel");
		System.out.println("[2] Tesoura");
		System.out.println("[3] Lagarto");
		System.out.println("[4] Spock");
		System.out.println("Opção : ");
	
		return console.nextInt();
	
	}// Fim do método lerOpcaoUsuario();
	

	public static void main(String[] args) {
		
		int jogador = lerOpcaoUsuario();
		int computador = obterOpcaoComputador();
		
		
		System.out.printf("Jogador 1 : %s", opcoes[jogador]);
		System.out.println("\n");
		
		System.out.printf("Computador: %s", opcoes[computador]);
		System.out.println("\n");
		
		if(REGRAS_DO_JOGO[jogador][computador] == GANHOU) {
		  System.out.println("Parabéns você ganhou!");
		}
		else if (REGRAS_DO_JOGO[jogador][computador] == EMPATOU) {
			System.out.println("Empate");
		}	
		else if (REGRAS_DO_JOGO[jogador][computador] == PERDEU) {
			System.out.println("O computador ganhou!");
		}	
		
		
	} // Fim do método Main

} // Fim da Classe Main
