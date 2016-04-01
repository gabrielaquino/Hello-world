# Exercicios
* Este Git-hub é apenas inclusão de exercicios realizados na faculdade
* Obrigado.
* 
###########################    EXERCICIOS   ###########################

1. (0,2)Fazer um programa em JAVA que leia um número inteiro e exiba o seu antecessor e o seu sucessor

       package LerInteiro;
 /**
 *
 * @author Gabriel Aquino
 */
import java.util.Scanner;
import javax.swing.JOptionPane;
    public class exercicio1 {
        public static void main(String[] args) {
         // Declaração das variaveis
            int a, sucessor, antecessor;
         //Declaração da classe Scanner        
            a = exercicio1.entradaNumero("Digite um o numero para saber seu sucessor e se antecessor");
                sucessor   = a + 1;             
                antecessor = a - 1;
         // Laço para controlar que não seja informado antecessores negativos  
            if(a == 0){
             //Envia Mensagem informando o sucessor de 0         
                mensagem("O numero informado "+ a +" só contem sucessor que é :"+ sucessor);                
             //Fim da prieira condição do programa           
                }else{
                 //Envia Mensagem informando o antecessor e sucessor de numeros maiores que 0
                     mensagem("O antecessor de"+ a + "é :"+ antecessor + "e seu sucessor é :"+ sucessor );
                    }   
             //fim da execução
             System.exit(0);
          }         
        /**
         * Substitui o codigo Imput do JOptionpane por entradaNumero
         * @param Mensagem a ser exibida
         */
        private static int entradaNumero(String mensagem){
            mensagem = JOptionPane.showInputDialog(null,mensagem);
        return Integer.parseInt(mensagem);
        }    
        /**
         * Substitui o codigo de JOptionPane por Mensagem
         * @param Mensagem a ser exibida
         */
        private static void mensagem(String Mensagem){
         JOptionPane.showMessageDialog(null,Mensagem);
         }
}
2. (0,3)Fazer um programa em JAVA que leia quatro notas de um aluno, calcule a média aritmética e imprima uma mensagem dizendo a situação final do aluno, de acordo com os critérios abaixo: MÉDIA < 5 RETIDO MÉDIA >= 5 e MÉDIA < 7 NEF MÉDIA >= 7 APROVADO

 package LeiaNota;
/**
*
* @author Gabriel
*/
import javax.swing.JOptionPane;
    public class Exercicios {
    /**
    * corpo principal
    * @param args the command line arguments
    */
        public static void main(String[] args) {
            //Declaração das variaveis
              float[] nota;
              nota = new float[4];
              float media;
              int i = 0;
            // Solicita as notas do aluno
              nota[0] = recebeNota("Por favor, informe a Primeira nota do aluno");
              nota[1] = recebeNota("Por favor, informe a Segunda  nota do aluno");
              nota[2] = recebeNota("Por favor, informe a Terceira nota do aluno");
              nota[3] = recebeNota("Por favor, informe a Quarta   nota do aluno");
            //recebe o valor da média
              media = calculaMedia(nota);
            //laço que informa a situação do aluno
              if(media < 5){
                    JOptionPane.showMessageDialog(null,"Retido");
                }else{
                    if(media >= 5 && media < 7){
                        JOptionPane.showMessageDialog(null,"NEF");
                    }else{
                       JOptionPane.showMessageDialog(null,"Aprovado");
                    }
                  }  
              }
              //Solicita e atribui um valor a variavel recebeNota
        public static float recebeNota(String mensagem){
             mensagem = JOptionPane.showInputDialog(mensagem);
               return Float.parseFloat(mensagem);        
            }
            /**
            * Calculo da média das notas
            * @param nota
            * @return media / i 
            */
        public static float calculaMedia(float[] nota){
        //Declaração de Variaveis
            int i = 0;
            float media = 0;
        //corre dentro do array
            for(i = 0; i < nota.length; i++){
                media = media + nota[i];
              }
            return(media / i);
        }
}


3. (0,5) A partir de n números lidos escrever como resultado a soma destes n números, a média e a soma dos quadrados e a soma dos cubos destes n números lidos. O primeiro numero a lido será o "n" para que o programa saiba quantos números vai ler em seguida.


package LeituraN-Numeros;
/**
 *
 * @author Gabriel
 */
import javax.swing.JOptionPane;
public class Aprendizado {
    public static void main(String[] args) {
        int i    = 0;
        int temp = 0;
        float quadrado = 0,
              cubo = 0;
        
        do{
            
           i = Aprendizado.qtdNumeros("Insira a quantidade de numeros a serem contabilizados");
        
        }while(i == 0);
        
        int[] recebeQtdNumeros;
        recebeQtdNumeros = new int[i];
        
        for(int j = 0; j < recebeQtdNumeros.length; j++) {
            recebeQtdNumeros[j] = Aprendizado.qtdNumeros("Insira um numero");
            //soma dos numeros dentro do Array
            temp +=  recebeQtdNumeros[j];
            // calculo do cubo
            cubo += Math.pow(recebeQtdNumeros[j],3);
            //calculo do quadrado
            quadrado += Math.pow(recebeQtdNumeros[j],2);
         } 
        // Apresenta os resultados
        mensagem("A somas dos numeros é "+  temp
                + "\nA média dos numeros é :" + (temp /recebeQtdNumeros.length)
                + "\nO cubo da soma é  :" + cubo
                + "\nO quadrado da soma é :" + quadrado );
    System.exit(0);
    }  
    /**
     * Não mexer 
     * @param mensagem 
     */
    public static void mensagem(String mensagem) {
       JOptionPane.showMessageDialog(null,mensagem);
    }
    public static int qtdNumeros(String mensagem) {
        mensagem = JOptionPane.showInputDialog(mensagem);
        return Integer.parseInt(mensagem);       
    }
 }

 

