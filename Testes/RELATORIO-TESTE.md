Bruno Picorallo Palotta RM80790

#	JUNIT
-------------------------------------------------------------------------
class JulgamentoPrisioneiroTest {
	
	JulgamentoPrisioneiro JP = new JulgamentoPrisioneiro();
	@Test
	void testCalculaPenaMutua() {
		int resultadoEsperado = 5;
		int resultadoReal = JP.calculaPena("Culpado", "Culpado");
		assertEquals(resultadoEsperado, resultadoReal);
	}
	
	@Test
	void testCalculaInocencia() {
		int resultadoEsperado = 0;
		int resultadoReal = JP.calculaPena("Inocente", "Inocente");
		assertEquals(resultadoEsperado, resultadoReal);
	}
	
	@Test
	void testCalculaPenaIndividual() {
		int resultadoEsperado = 10;
		int resultadoReal = JP.calculaPena("Culpado", "Inocente");
		assertEquals(resultadoEsperado, resultadoReal);
	}
	
	@Test
	void testCalculaPenaCumplices() {
		int resultadoEsperado = 1;
		int resultadoReal = JP.calculaPena("Inocente", "Culpado");
		assertEquals(resultadoEsperado, resultadoReal);
	}
}

#	Classe Arrumada
--------------------------------------------------------------------------------------
	public class JulgamentoPrisioneiro {
	private int PENA_INOCENCIA = 0;
	private int PENA_CONDENACAO_MUTUA = 5;
	private int PENA_CONDENACAO_INDIVIDUAL = 10;
	private int PENA_CONDENACAO_CUMPLICES = 1;

	public int calculaPena(String StringPrisioneiroA, String StringPrisioneiroB) {
		if (StringPrisioneiroA.equalsIgnoreCase("Culpado")) {
			if (StringPrisioneiroB.equalsIgnoreCase("Culpado")){
				return PENA_CONDENACAO_MUTUA;
			} else {
				return PENA_CONDENACAO_INDIVIDUAL;
			}
		}
		else {
			if (StringPrisioneiroB.equalsIgnoreCase("Culpado")){
				return PENA_CONDENACAO_CUMPLICES;
			} else {
				return PENA_INOCENCIA;
			}
		}
	}
}
1º Método
Classe Resposta não existe
2º Método
Classe Resposta não existe
3º Método
Classe Resposta não existe
4º Método
Classe Resposta não existe
