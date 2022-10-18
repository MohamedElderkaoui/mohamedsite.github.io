---
title: "Miproyecto"
date: 2022-10-06T13:19:30+02:00
---
## he trabajado con 
# java y javadoc y junittext
```java
package Funcion;





/**
 * 
 * @author Mohamed el Derkaoui Merzouk Bendoukha 1iN_DAWD
 *
 */
public class Utilidad {

	/**
	 * 
	 * @param width
	 * @param s
	 * @return
	 */
	public static String c(int width, String s) {
		return String.format("%-" + width + "s", String.format("%" + (s.length() + (width - s.length()) / 2) + "s", s));
	}

	public static String c(int width, int s) {
		return String.format("%-" + width + "s",String.format("%" + (("" + s).length() + (width - ("" + s).length()) / 2) + "s", s));
	}
	public static String c1(int width, int s) {
		return String.format("%-" + width + "s|",String.format("%" + (("" + s).length() + (width - ("" + s).length()) / 2) + "s", s));
	}

	/**
	 * @param d2
	 * @param d3
	 * @return boolean d2 * boolean d3
	 */
	public static boolean y(boolean d2, boolean d3) {
		return d2 && d3;
	}

	/**
	 * @param d2
	 * @param d3
	 * @return boolean d2+boolean d3
	 */
	public static boolean o(boolean d2, boolean d3) {
		return d2 || d3;
	}

	/**
	 * 
	 * @return leer
	 */
	public static Leer leer() {
		Leer leer = new Leer();
		return leer;

	}

	/**
	 * +int[] ordernadore(int[] vector)
	 * 
	 * @param vector
	 */
	public static int[] ordernadore(int[] vector) {
		for (int i = 0; i < vector.length; i++) {
			for (int j = 0; j < (vector.length - 1); j++) {
				int apoyo;
				if (vector[j] > vector[j + 1]) {
					apoyo = vector[j];
					vector[j] = vector[j + 1];
					vector[j + 1] = apoyo;
				}
			}
		}
		return vector;
	}

	/**
	 * 
	 * @param numero
	 * @param i
	 * @param j
	 * @return i>numero>j
	 */
	public static boolean intervalo(int numero, int i, int j) {
		return (numero < i) || (numero > j);
	}

	/**
	 * 
	 * @param numero
	 * @param i
	 * @param j
	 * @return i>numero>j
	 */
	public static boolean iintervalo1(int numero, int i, int j) {
		boolean b = (numero < i) || (numero > j);
		return !b;
	}

	/**
	 * 
	 * @param numero
	 * @param i
	 * @param j
	 * @return i>numero>j
	 */

	public static boolean no_o_intervalo(int numero, int i, int j) {
		boolean b = (numero < i) && (numero > j);
		return !b;
	}

	/**
	 * 
	 * @param numero
	 * @param i
	 * @param j
	 * @return i>numero>j
	 */

	public static boolean o_intervalo(int numero, int i, int j) {
		boolean b = (numero < i) && (numero > j);
		return b;
	}

	/**
	 * @param numero
	 * @param i
	 * @param j
	 * @return i>numero>j
	 */
	public static boolean intervalo(int numero, int i) {
		return (numero < i);
	}
}
    
/*

Proyecto Hundir La Flota 
--------------------------------- 
1 | | | | | | | | | 
--------------------------------- 
2 | | | | | | | | | 
--------------------------------- 
3 | | | | | | | | | 
--------------------------------- 
4 | | | | | | | | | 
--------------------------------- 
5 | | | | | | | | | 
--------------------------------- 
6 | | | | | | | | | 
--------------------------------- 
7 | | | | | | | | | 
--------------------------------- 
8 | | | | | | | | | 
--------------------------------- 
a b c d e f g h 
Se trata de reproducir el clásico juego de hundir la  flota. Para ello se generaran dos tableros de 8x8 para  cada usuario (usuario vs máquina). En un tablero se  llevará el control de las tiradas hechas por el propio  usuario y en el segundo tablero se controlarán las  tiradas generadas por la máquina y los barcos propios. 
El juego consiste en introducir coordenadas por turnos  y hundir los barcos del oponente. Las coordenadas  indican la posición donde se tira un torpedo, en caso  de no acertar con la posición de algún barco, saldrá un  mensaje que indicará que no ha pasado nada “Agua”. En  caso de acertar, el mensaje puede variar. Puede ser  “Tocado” si todavía tiene partes salvadas o “Hundido”  cuando ya no le quedan posiciones sin tocar. 
Los turnos se irán alternando entre el jugador y la  máquina. En caso de acertar con la posición de un barco  (tocado o hundido) el usuario o máquina tendrá un turno  extra (hasta que falle).
Curso 2021/2022 Daniel Val 
Juego 2Ev 
El programa se puede realizar de la forma que se  quiera, pero que permita jugar. Queda a elección del  programador el uso de clases, métodos, estructuras,  etc.. Aunque sí que se recomienda seguir cierto orden  de implementación. 
En el nivel fácil, se implementarán 2 barcos de 2  posiciones y en el nivel difícil, se implementarán 2  barcos de 2 posiciones y un barco de 3 posiciones. 
Orden sugerido: 

*/
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Iterator;
import java.util.List;

import Funcion.Utilidad;

/**
 * 
 */

/**
 * @author mohamed Derkaoui Merzouk benkhadou
 *
 */
public class Principal {
	private static String agua = "≋≋";
	private static String brocle = "🛥🛥";
	private static String toco = "≋🛥";

	/**
	 * @param args
	 */
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		String[][][] miflota = mapa();
		int length = miflota.length;
		int length2 = 1;
		cargar(miflota, length);
		int mipunto = 1;
		int cpupunto = 1;

		String[] menu = { "salir", "Facil", "dificu" };
		int opcion = -1;
		do {
			if (opcion == 1) {
				ponenmi(miflota);
				generetmapacpu(miflota);
				mipunto = 6;
				cpupunto = 6;
				List<String> apuntadoList = juegarList(miflota, mipunto, cpupunto);

				apuntadoList.forEach((i) -> System.out.println(i));
				mapa(miflota);

			} else if (opcion == 2) {
				ponenmi3(miflota);
				ponencpu3(miflota);
				mipunto = 7;
				cpupunto = 7;
				List<String> apuntadoList = juegarList(miflota, mipunto, cpupunto);
				apuntadoList.forEach((i) -> System.out.println(i));
				mapa(miflota);

			} else if (opcion == 0) {
				break;
			}
			opcion = Utilidad.leer().leer_opcion_menu("", menu);
		} while (true);
		mapa(miflota);

		/*
		 * String t = ""; t+=imprimir(miflota); System.out.println(t);
		 */

	}

	public static String[][][] mapa() {
		String[][][] miflota = new String[4][8][8];
		return miflota;
	}

	/**
	 * @param miflota
	 * @param mipunto
	 * @param cpupunto
	 * @return
	 */
	public static List<String> juegarList(String[][][] miflota, int mipunto, int cpupunto) {
		String pont = "";
		List<String> apuntadoListmi = new ArrayList<>();
		List<String> apuntadoListcpu = new ArrayList<>();
		int splitpont_x = -1;
		int splitpont_y = -1;
		/**
		 * 
		 * String[][] mb = tablerios[0]; String[][] mdisparo = tablerios[1]; String[][]
		 * Cpub = tablerios[2]; String[][] cpudisparo = tablerios[3];
		 */
		do {

			mipunto = miturno(miflota, mipunto, apuntadoListmi);

			cpupunto = turnoncpu(miflota, cpupunto, apuntadoListcpu);

			if (mipunto == 0) {
				System.out.println("gana tu");
				break;
			}
			if (cpupunto == 0) {
				System.out.println("game over");
				break;
			}
		} while (true);
		return apuntadoListmi;
	}

	public static int turnoncpu(String[][][] miflota, int cpupunto, List<String> apuntadoListcpu) {
		System.out.println("");
		String pont;
		int splitpont_x;
		int splitpont_y;
		pont = String.format("(%d,%d)", (int) (Math.random() * 8), (int) (Math.random() * 8));
		if (!apuntadoListcpu.contains(pont)) {
			if (pont.matches("\\([0-7]{1}\\,[0-7]{1}\\)")) {
				String[] splitpont = pont.split("[\\(\\,\\)]");

				System.out.println(1);
				splitpont_x = Integer.parseInt(splitpont[1]);
				splitpont_y = Integer.parseInt(splitpont[2]);
				if (miflota[2][splitpont_y][splitpont_x].compareTo("x") != 0) {
					if (miflota[0][splitpont_y][splitpont_x].compareTo(brocle) == 0) {
						miflota[0][splitpont_y][splitpont_x] = toco;
						miflota[2][splitpont_y][splitpont_x] = "x";
						cpupunto--;
						cpupunto = turnoncpu(miflota, cpupunto, apuntadoListcpu);

					} else {
						miflota[1][splitpont_y][splitpont_x] = "x";

					}
				}
			}
		}
		return cpupunto;
	}

	public static int miturno(String[][][] miflota, int mipunto, List<String> apuntadoListmi) {
		System.out.println("");
		String pont;
		int splitpont_x;
		int splitpont_y;
		do {
			pont = Utilidad.leer().leerCadena("TU");
			if (!apuntadoListmi.contains(pont)) {
				if (pont.matches("\\([0-7]{1}\\,[0-7]{1}\\)")) {
					String[] splitpont = pont.split("[\\(\\,\\)]");

					splitpont_x = Integer.parseInt(splitpont[1]);
					splitpont_y = Integer.parseInt(splitpont[2]);
					if (miflota[3][splitpont_y][splitpont_x].compareTo(brocle) == 0) {
						if (miflota[1][splitpont_y][splitpont_x].compareTo("x") != 0) {
							miflota[3][splitpont_y][splitpont_x] = toco;
							miflota[1][splitpont_y][splitpont_x] = "x";
							apuntadoListmi.add(pont);
							mipunto = miturno(miflota, mipunto, apuntadoListmi);

							mipunto--;
							break;
						} else {
							miflota[1][splitpont_y][splitpont_x] = "x";
							apuntadoListmi.add(pont);
						}
					}
				}
			}
			mapa(miflota);
			return mipunto;
		} while (!apuntadoListmi.contains(pont));
		return mipunto;
	}

	/**
	 * @param miflota
	 * @param mipunto
	 * @param cpupunto
	 * @return
	 */
	public static List<String> juegarList_4(String[][][] miflota, int mipunto, int cpupunto) {
		String pont = "";
		List<String> apuntadoListmi = new ArrayList<>();
		List<String> apuntadoListcpu = new ArrayList<>();
		int splitpont_x = -1;
		int splitpont_y = -1;
		/**
		 * 
		 * String[][] mb = tablerios[0]; String[][] mdisparo = tablerios[1]; String[][]
		 * Cpub = tablerios[2]; String[][] cpudisparo = tablerios[3];
		 */
		for (int h = 0; h <= 1; h++) {
			for (int i = 0; i <= 1; i++) {
				pont = Utilidad.leer().leerCadena("(#,#)");
				if (!apuntadoListmi.contains(pont)) {
					if (pont.matches("\\([0-7]{1}\\,[0-7]{1}\\)")) {
						String[] splitpont = pont.split("[\\(\\,\\)]");

						splitpont_x = Integer.parseInt(splitpont[1]);
						splitpont_y = Integer.parseInt(splitpont[2]);
						if (miflota[1][splitpont_y][splitpont_x].compareTo("x") != 0) {
							if (miflota[3][splitpont_y][splitpont_x].compareTo(brocle) == 0) {
								miflota[3][splitpont_y][splitpont_x] = toco;
								miflota[1][splitpont_y][splitpont_x] = "x";
								i--;
								mipunto--;
							} else {
								miflota[1][splitpont_y][splitpont_x] = "x";
							}
						}
					}
				}
			}
			for (int i = 0; i <= 1; i++) {
				pont = String.format("(%d,%d)", (int) (Math.random() * 8), (int) (Math.random() * 8));
				if (!apuntadoListcpu.contains(pont)) {
					if (pont.matches("\\([0-7]{1}\\,[0-7]{1}\\)")) {
						String[] splitpont = pont.split("[\\(\\,\\)]");

						splitpont_x = Integer.parseInt(splitpont[1]);
						splitpont_y = Integer.parseInt(splitpont[2]);
						if (miflota[2][splitpont_y][splitpont_x].compareTo("x") != 0) {
							if (miflota[0][splitpont_y][splitpont_x].compareTo(brocle) == 0) {
								miflota[0][splitpont_y][splitpont_x] = toco;
								miflota[2][splitpont_y][splitpont_x] = "x";
								cpupunto--;
								i--;

							} else {
								miflota[1][splitpont_y][splitpont_x] = "x";
							}
						}
					}
				}
			}
			if (mipunto == 0) {
				System.out.println("gana tu");
				return apuntadoListmi;
			}
			if (cpupunto == 0) {
				System.out.println("game over");
				return apuntadoListmi;

			}
		}
		while (true)
			;
	}

	public static void ponencpu3(String[][][] miflota) {
		String pont = "";
		List<String> apuntadoList = new ArrayList<>();
		int splitpont_x = -1;
		int splitpont_y = -1;
		for (int i = 0; i < 2; i++) {
			do {
				pont = String.format("(%d,%d)", (int) (Math.random() * 8), (int) (Math.random() * 8));
				if (!apuntadoList.contains(pont)) {
					if (pont.matches("\\([0-7]{1}\\,[0-7]{1}\\)")) {
						String[] splitpont = pont.split("[\\(\\,\\)]");

						splitpont_x = Integer.parseInt(splitpont[1]);
						splitpont_y = Integer.parseInt(splitpont[2]);
						if (miflota[2][splitpont_y][splitpont_x].compareTo(brocle) != 0) {
							miflota[2][splitpont_y][splitpont_x] = brocle;
							int opcion = -1;
							apuntadoList.add(pont);
							do {
								if (opcion == 1) {
									if (splitpont_y - 1 > -1) {
										if (miflota[2][splitpont_y - 1][splitpont_x].compareTo(brocle) != 0) {
											miflota[2][splitpont_y - 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y - 1));
											break;
										}
									}
								} else if (opcion == 2) {
									if (splitpont_y + 1 < miflota[2].length) {
										if (miflota[2][splitpont_y + 1][splitpont_x].compareTo(brocle) != 0) {
											miflota[2][splitpont_y + 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y + 1));
											break;
										}
									}
								} else if (opcion == 3) {
									if (splitpont_x - 1 > -1) {
										if (miflota[2][splitpont_y - 1][splitpont_x].compareTo(brocle) != 0) {
											miflota[2][splitpont_y][splitpont_x - 1] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x - 1, splitpont_y));
											break;
										}
									}
								} else if (opcion == 4) {
									if (splitpont_x + 1 < miflota[2][splitpont_y].length) {
										if (miflota[2][splitpont_y][splitpont_x + 1].compareTo(brocle) != 0) {
											miflota[2][splitpont_y][splitpont_x + 1] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x - 1, splitpont_y));
											break;
										}
									}

								}
								opcion = (int) ((Math.random() * 4) + 1);
							} while (true);
							break;
						}

					}
				}
			} while (true);
		} // for (int i = 0; i < 2; i++)
		do {
			pont = String.format("(%d,%d)", (int) (Math.random() * 8), (int) (Math.random() * 8));
			if (!apuntadoList.contains(pont)) {
				if (pont.matches("\\([0-7]{1}\\,[0-7]{1}\\)")) {
					String[] splitpont = pont.split("[\\(\\,\\)]");

					splitpont_x = Integer.parseInt(splitpont[1]);
					splitpont_y = Integer.parseInt(splitpont[2]);
					if (miflota[2][splitpont_y][splitpont_x].compareTo(brocle) != 0) {
						miflota[2][splitpont_y][splitpont_x] = brocle;
						int opcion = -1;
						apuntadoList.add(pont);
						do {
							if (opcion == 1) {
								if (splitpont_y - 1 > -1) {
									if (miflota[2][splitpont_y - 2][splitpont_x].compareTo(brocle) != 0) {
										if (miflota[2][splitpont_y - 1][splitpont_x].compareTo(brocle) != 0) {
											miflota[2][splitpont_y - 2][splitpont_x] = brocle;
											miflota[2][splitpont_y - 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y - 2));
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y - 1));
											break;
										}
									}
								}
							} else if (opcion == 2) {
								if (splitpont_y + 1 < miflota[2].length) {
									if (miflota[2][splitpont_y + 2][splitpont_x].compareTo(brocle) != 0) {
										if (miflota[2][splitpont_y + 1][splitpont_x].compareTo(brocle) != 0) {
											miflota[2][splitpont_y + 2][splitpont_x] = brocle;
											miflota[2][splitpont_y + 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y + 2));
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y + 1));
											break;
										}
									}
								}
							} else if (opcion == 3) {
								if (splitpont_x - 2 < -1) {
									if (miflota[2][splitpont_y][splitpont_x - 2].compareTo(brocle) != 0) {
										if (miflota[2][splitpont_y][splitpont_x - 1].compareTo(brocle) != 0) {
											miflota[2][splitpont_y][splitpont_x - 2] = brocle;
											miflota[2][splitpont_y][splitpont_x - 1] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x - 2, splitpont_y));
											apuntadoList.add(String.format("(%d,%d)", splitpont_x - 1, splitpont_y));
											break;
										}
									}
								}
							} else if (opcion == 4) {
								if (splitpont_x + 2 > miflota[2][splitpont_y].length) {
									if (miflota[2][splitpont_y][splitpont_x + 2].compareTo(brocle) != 0) {
										if (miflota[2][splitpont_y][splitpont_x + 1].compareTo(brocle) != 0) {
											miflota[2][splitpont_y][splitpont_x + 1] = brocle;
											miflota[2][splitpont_y][splitpont_x + 2] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x + 2, splitpont_y));
											apuntadoList.add(String.format("(%d,%d)", splitpont_x + 1, splitpont_y));
											break;
										}
									}
								}

							}
							opcion = (int) ((Math.random() * 4) + 1);
						} //
						while (true);
						break;
					}

				}
			}
		} while (true);

	}

	public static void ponenmi3(String[][][] miflota) {
		String pont = "";
		List<String> apuntadoList = new ArrayList<>();
		int splitpont_x = -1;
		int splitpont_y = -1;
		for (int i = 0; i < 2; i++) {
			do {
				pont = Utilidad.leer().leerCadena("(#,#)");
				if (!apuntadoList.contains(pont)) {
					if (pont.matches("\\([0-7]{1}\\,[0-7]{1}\\)")) {
						String[] splitpont = pont.split("[\\(\\,\\)]");

						splitpont_x = Integer.parseInt(splitpont[1]);
						splitpont_y = Integer.parseInt(splitpont[2]);
						if (miflota[0][splitpont_y][splitpont_x].compareTo(brocle) != 0) {
							miflota[0][splitpont_y][splitpont_x] = brocle;
							String t = "";
							t += imprimir(miflota);
							System.out.print(t);
							miflota[0][splitpont_y][splitpont_x] = brocle;
							String[] menu = { " ", "arriba", "abajo", "derecha", "izquiedad" };
							int opcion = -1;
							apuntadoList.add(pont);
							do {
								if (opcion == 1) {
									if (splitpont_y - 1 > -1) {
										if (miflota[0][splitpont_y - 1][splitpont_x].compareTo(brocle) != 0) {
											System.out.println("arriba");
											miflota[0][splitpont_y - 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y - 1));
											mapa(miflota);
											break;
										} else {
											System.out.println("error posicion");
										}
									}
								} else if (opcion == 2) {
									if (splitpont_y + 1 < miflota[0].length) {
										if (miflota[0][splitpont_y + 1][splitpont_x].compareTo(brocle) != 0) {
											System.out.println("abajo");
											miflota[0][splitpont_y + 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y + 1));
											mapa(miflota);
											break;
										} else {
											System.out.println("error posicion");
										}
									}
								} else if (opcion == 3) {
									if (splitpont_x - 1 > -1) {
										if (miflota[0][splitpont_y - 1][splitpont_x].compareTo(brocle) != 0) {
											System.out.println("derecha");
											miflota[0][splitpont_y][splitpont_x - 1] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x - 1, splitpont_y));
											apuntadoList.forEach((i2) -> System.out.println(i2));
											mapa(miflota);
											break;
										} else {
											System.out.println("error posicion");
										}
									}
								} else if (opcion == 4) {
									if (splitpont_x + 1 < miflota[0][splitpont_y].length) {
										if (miflota[0][splitpont_y][splitpont_x + 1].compareTo(brocle) != 0) {
											System.out.println("derecha");
											miflota[0][splitpont_y][splitpont_x + 1] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x - 1, splitpont_y));
											apuntadoList.forEach((i2) -> System.out.println(i2));
											mapa(miflota);
											break;
										} else {
											System.out.println("error posicion");
										}
									}

								}
								opcion = (int) (Math.random() * 4);
							} while (true);
							break;
						}

					}
				}
			} while (true);
		} // for (int i = 0; i < 2; i++)
		do {
			pont = Utilidad.leer().leerCadena("(#,#)");
			if (!apuntadoList.contains(pont)) {
				if (pont.matches("\\([0-7]{1}\\,[0-7]{1}\\)")) {
					String[] splitpont = pont.split("[\\(\\,\\)]");

					splitpont_x = Integer.parseInt(splitpont[1]);
					splitpont_y = Integer.parseInt(splitpont[2]);
					if (miflota[0][splitpont_y][splitpont_x].compareTo(brocle) != 0) {
						String t = "";
						t += imprimir(miflota);
						System.out.print(t);
						miflota[0][splitpont_y][splitpont_x] = brocle;
						String[] menu = { " ", "arriba", "abajo", "derecha", "izquiedad" };
						int opcion = -1;
						apuntadoList.add(pont);
						apuntadoList.forEach((i) -> System.out.println(i));
						mapa(miflota);
						do {
							if (opcion == 1) {
								if (splitpont_y - 1 > -1) {
									if (miflota[0][splitpont_y - 2][splitpont_x].compareTo(brocle) != 0) {
										if (miflota[0][splitpont_y - 1][splitpont_x].compareTo(brocle) != 0) {
											miflota[0][splitpont_y - 2][splitpont_x] = brocle;
											miflota[0][splitpont_y - 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y - 2));
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y - 1));
											apuntadoList.forEach((i) -> System.out.println(i));
											mapa(miflota);
											break;
										} else {
											System.out.println("error posicion");
										}
									} else {
										System.out.println("error posicion");
									}
								}
							} else if (opcion == 2) {
								if (splitpont_y + 1 < miflota[0].length) {
									if (miflota[0][splitpont_y + 2][splitpont_x].compareTo(brocle) != 0) {
										if (miflota[0][splitpont_y + 1][splitpont_x].compareTo(brocle) != 0) {
											miflota[0][splitpont_y + 2][splitpont_x] = brocle;
											miflota[0][splitpont_y + 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y + 2));
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y + 1));
											apuntadoList.forEach((i) -> System.out.println(i));
											mapa(miflota);
											break;
										}
									} else {
										System.out.println("error posicion");
									}
								}
							} else if (opcion == 3) {
								if (splitpont_x - 2 < -1) {
									if (miflota[0][splitpont_y][splitpont_x - 2].compareTo(brocle) != 0) {
										if (miflota[0][splitpont_y][splitpont_x - 1].compareTo(brocle) != 0) {
											miflota[0][splitpont_y][splitpont_x - 2] = brocle;
											miflota[0][splitpont_y][splitpont_x - 2] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x - 2, splitpont_y));
											apuntadoList.add(String.format("(%d,%d)", splitpont_x - 1, splitpont_y));
											apuntadoList.forEach((i) -> System.out.println(i));
											mapa(miflota);
											break;
										} else {
											System.out.println("error posicion");
										}
									} else {
										System.out.println("error posicion");
									}
								}
							} else if (opcion == 4) {
								if (splitpont_x + 2 > miflota[0][splitpont_y].length) {
									if (miflota[0][splitpont_y][splitpont_x + 2].compareTo(brocle) != 0) {
										if (miflota[0][splitpont_y][splitpont_x + 1].compareTo(brocle) != 0) {
											miflota[0][splitpont_y][splitpont_x + 1] = brocle;
											miflota[0][splitpont_y][splitpont_x + 2] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x + 2, splitpont_y));
											apuntadoList.add(String.format("(%d,%d)", splitpont_x + 1, splitpont_y));
											apuntadoList.forEach((i) -> System.out.println(i));
											mapa(miflota);
											break;
										} else {
											System.out.println("error posicion");
										}
									} else {
										System.out.println("error posicion");
									}
								}

							}
							opcion = (int) (Math.random() * 4);
						} while (true);
						break;
					}

				}
			}
		} while (true);
		apuntadoList.forEach((i) -> System.out.println(i));
		String t = "";
		t += imprimir(miflota);
		System.out.print(t);
	}

	public static void mapa(String[][][] miflota) {
		String tt = "";
		tt += imprimirmi(miflota);
		System.out.print(tt);
	}

	/* drtt(),8,8 */
	/**
	 * imprimir tabla
	 * 
	 * @param tablerios
	 * @return
	 */
	public static String imprimir(String[][][] tablerios) {
		// TODO Auto-generated method stub

		String[][] mb = tablerios[0];
		String[][] mdisparo = tablerios[1];
		String[][] Cpub = tablerios[2];
		String[][] cpudisparo = tablerios[3];
		String t = "";
		String tl = "";
		int length = tl.length();
		for (int i = 0; i < mb.length; i++) {
			tl = "";
			tl += String.format("%s|", Utilidad.c(drtt(), i + 1));
			for (int j = 0; j < mb[i].length; j++) {
				String casilla_mb = mb[i][j];
				tl += String.format("%s|", Utilidad.c(drtt(), casilla_mb));
			}
			tl += String.format("%s|", Utilidad.c(drtt(), i + 1));
			for (int j = 0; j < mdisparo[i].length; j++) {
				String casilla_mdisparo = mdisparo[i][j];
				tl += String.format("%s|", Utilidad.c(drtt(), casilla_mdisparo));
			}
			tl += String.format("%s|", Utilidad.c(10, ""));
			tl += String.format("%s|", Utilidad.c(drtt(), i + 1));
			for (int j = 0; j < Cpub[i].length; j++) {
				String casilla_Cpub = Cpub[i][j];
				tl += String.format("%s|", Utilidad.c(drtt(), casilla_Cpub));
			}
			tl += String.format("%s|", Utilidad.c(drtt(), i + 1));

			for (int j = 0; j < cpudisparo[i].length; j++) {
				String casilla_cpudisparo = cpudisparo[i][j];
				tl += String.format("%s|", Utilidad.c(drtt(), casilla_cpudisparo));
			}
			length = tl.length();
			tl += "\n";

			tl += Utilidad.c(length, " ").replace(" ", "-");
			tl += "\n";

			t += tl;
		}

		tl = ddd(tl);
		tl += "\n";
		t += tl;
		return t;
	}/* drtt(),8,8 */

	public static void generetmapacpu(String[][][] miflota) {
		String pont = "";
		List<String> apuntadoList = new ArrayList<>();
		int splitpont_x = -1;
		int splitpont_y = -1;
		for (int i = 0; i < 3; i++) {
			do {
				pont = String.format("(%d,%d)", (int) (Math.random() * 8), (int) (Math.random() * 8));
				if (!apuntadoList.contains(pont)) {
					if (pont.matches("\\([0-7]{1}\\,[0-7]{1}\\)")) {
						String[] splitpont = pont.split("[\\(\\,\\)]");

						splitpont_x = Integer.parseInt(splitpont[1]);
						splitpont_y = Integer.parseInt(splitpont[2]);
						if (miflota[2][splitpont_y][splitpont_x].compareTo(brocle) != 0) {
							miflota[2][splitpont_y][splitpont_x] = brocle;
							String[] menu = { " ", "arriba", "abajo", "derecha", "izquiedad" };
							int opcion = -1;
							apuntadoList.add(pont);
							do {
								if (opcion == 1) {
									if (splitpont_y - 1 > -1) {
										if (miflota[2][splitpont_y - 1][splitpont_x].compareTo(brocle) != 0) {
											miflota[2][splitpont_y - 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y - 1));
											break;
										}
									}
								} else if (opcion == 2) {
									if (splitpont_y + 1 < miflota[2].length) {
										if (miflota[2][splitpont_y + 1][splitpont_x].compareTo(brocle) != 0) {
											miflota[2][splitpont_y + 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y + 1));
											break;
										}
									}
								} else if (opcion == 3) {
									if (splitpont_x - 1 > -1) {
										if (miflota[2][splitpont_y][splitpont_x - 1].compareTo(brocle) != 0) {
											miflota[2][splitpont_y][splitpont_x - 1] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x - 1, splitpont_y));
											break;
										}
									}
								} else if (opcion == 4) {
									if (splitpont_x + 1 < miflota[2][splitpont_y].length) {
										if (miflota[2][splitpont_y][splitpont_x + 1].compareTo(brocle) != 0) {
											miflota[2][splitpont_y][splitpont_x + 1] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x + 1, splitpont_y));
											break;
										}
									}

								}
								opcion = ((int) (Math.random() * 4)) + 1;
							} while (true);
							break;
						}

					}
				}
			} //
			while (true);
		}
		apuntadoList.forEach((i) -> System.out.println(i));
	}

	/**
	 * 
	 * @param miflota
	 */
	public static void ponenmi(String[][][] miflota) {
		String pont = "";
		List<String> apuntadoList = new ArrayList<>();
		int splitpont_x = -1;
		int splitpont_y = -1;
		for (int i = 0; i < 3; i++) {
			do {
				pont = Utilidad.leer().leerCadena("(#,#)");// escribi con coordernada
				if (!apuntadoList.contains(pont)) {// si no hay estacoordernada lisr
					if (pont.matches("\\([0-7]{1}\\,[0-7]{1}\\)")) {// valida
						String[] splitpont = pont.split("[\\(\\,\\)]"); // saca losd

						splitpont_x = Integer.parseInt(splitpont[1]);//
						splitpont_y = Integer.parseInt(splitpont[2]);
						if (miflota[0][splitpont_y][splitpont_x].compareTo(brocle) != 0) {// valida si no hay barco
							miflota[0][splitpont_y][splitpont_x] = brocle;
							mapa(miflota);// imprimir
							String[] menu = { " ", "arriba", "abajo", "derecha", "izquiedad" };
							int opcion = -1;
							apuntadoList.add(pont);// añidir
							do {
								if (opcion == 1) {
									if (splitpont_y - 1 > -1) {
										if (miflota[0][splitpont_y - 1][splitpont_x].compareTo(brocle) != 0) {
											System.out.println("arriba");
											miflota[0][splitpont_y - 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y - 1));// añidir
											mapa(miflota);// imprimir
											break;
										} else {
											System.out.println("error posicion");
										}
									}
								} else if (opcion == 2) {
									if (splitpont_y + 1 < miflota[0].length) {
										if (miflota[0][splitpont_y + 1][splitpont_x].compareTo(brocle) != 0) {
											System.out.println("abajo");
											miflota[0][splitpont_y + 1][splitpont_x] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x, splitpont_y + 1));// añidir
											mapa(miflota);// imprimir
											break;
										} else {
											System.out.println("error posicion");
										}
									}
								} else if (opcion == 3) {
									if (splitpont_x - 1 > -1) {
										if (miflota[0][splitpont_y][splitpont_x - 1].compareTo(brocle) != 0) {
											System.out.println("derecha");
											miflota[0][splitpont_y][splitpont_x - 1] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x - 1, splitpont_y));// añidir
											mapa(miflota);// imprimir
											break;
										} else {
											System.out.println("error posicion");
										}
									}
								} else if (opcion == 4) {
									if (splitpont_x + 1 < miflota[0][splitpont_y].length) {
										if (miflota[0][splitpont_y][splitpont_x + 1].compareTo(brocle) != 0) {
											System.out.println("derecha");
											miflota[0][splitpont_y][splitpont_x + 1] = brocle;
											apuntadoList.add(String.format("(%d,%d)", splitpont_x + 1, splitpont_y));// añidir
											mapa(miflota);// imprimir
											break;
										} else {
											System.out.println("error posicion");
										}
									}

								}
								opcion = Utilidad.leer().leer_opcion_menu("", menu);
							} while (true);
							break;
						} else {
							System.out.println("error posicion");
						}

					}
				}
			} while (true);
		}
		apuntadoList.forEach((i) -> System.out.println(i));
		mapa(miflota);
	}

	/**
	 * para i
	 * 
	 * @param tablerios
	 * @return
	 */
	public static String imprimirmi(String[][][] tablerios) {
		// TODO Auto-generated method stub

		String[][] mb = tablerios[0];
		String[][] mdisparo = tablerios[1];
		String[][] Cpub = tablerios[2];
		String[][] cpudisparo = tablerios[3];
		String t = "";
		String tl = "";

		int length = tl.length();
		for (int i = 0; i < mb.length; i++) {
			tl = "";
			tl += String.format("%s|", Utilidad.c(drtt(), i + 1));
			for (int j = 0; j < mb[i].length; j++) {
				String casilla_mb = mb[i][j];
				tl += String.format("%s|", Utilidad.c(drtt(), casilla_mb));
			}
			tl += String.format("%s|", Utilidad.c(10, ""));
			tl += String.format("%s|", Utilidad.c(drtt(), i + 1));
			for (int j = 0; j < mdisparo[i].length; j++) {
				String casilla_mdisparo = mdisparo[i][j];
				tl += String.format("%s|", Utilidad.c(drtt(), casilla_mdisparo));
			}

			length = tl.length();
			tl += "\n";

			tl += Utilidad.c(length, " ").replace(" ", "-");
			tl += "\n";

			t += tl;
		}

		tl += String.format("%s|", Utilidad.c(drtt(), " "));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "b"));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "d"));
		tl += String.format("%s|", Utilidad.c(drtt(), "e"));
		tl += String.format("%s|", Utilidad.c(drtt(), "f"));
		tl += String.format("%s|", Utilidad.c(drtt(), "g"));
		tl += String.format("%s|", Utilidad.c(drtt(), "h"));

		tl += String.format("%s|", Utilidad.c(10, ""));
		tl += String.format("%s|", Utilidad.c(drtt(), ""));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "b"));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "d"));
		tl += String.format("%s|", Utilidad.c(drtt(), "e"));
		tl += String.format("%s|", Utilidad.c(drtt(), "f"));
		tl += String.format("%s|", Utilidad.c(drtt(), "g"));
		tl += String.format("%s|", Utilidad.c(drtt(), "h"));
		;
		tl += "\n";
		t += tl;
		return t;
	}/* drtt(),8,8 */

	/**
	 * imprime parte cup pc
	 * 
	 * @param tablerios
	 * @return
	 */
	public static String i2mprimircpu(String[][][] tablerios) {
		// TODO Auto-generated method stub

		String[][] mb = tablerios[0];
		String[][] mdisparo = tablerios[1];
		String[][] Cpub = tablerios[2];
		String[][] cpudisparo = tablerios[3];
		String t = "";
		String tl = "";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		int length = tl.length();
		for (int i = 0; i < mb.length; i++) {
			tl = "";

			tl += String.format("%s|", Utilidad.c(drtt(), i + 1));
			for (int j = 0; j < Cpub[i].length; j++) {
				String casilla_Cpub = Cpub[i][j];
				tl += String.format("%s|", Utilidad.c(drtt(), casilla_Cpub));
			}
			tl += String.format("%s|", Utilidad.c(10, ""));
			tl += String.format("%s|", Utilidad.c(drtt(), i + 1));
			for (int j = 0; j < cpudisparo[i].length; j++) {
				String casilla_cpudisparo = cpudisparo[i][j];
				tl += String.format("%s|", Utilidad.c(drtt(), casilla_cpudisparo));
			}

			length = tl.length();
			tl += "\n";

			tl += Utilidad.c(length, " ").replace(" ", "-");
			tl += "\n";

			t += tl;
		}

		tl += String.format("%s|", Utilidad.c(drtt(), " "));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "b"));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "d"));
		tl += String.format("%s|", Utilidad.c(drtt(), "e"));
		tl += String.format("%s|", Utilidad.c(drtt(), "f"));
		tl += String.format("%s|", Utilidad.c(drtt(), "g"));
		tl += String.format("%s|", Utilidad.c(drtt(), "h"));

		tl += String.format("%s|", Utilidad.c(10, ""));
		tl += String.format("%s|", Utilidad.c(drtt(), ""));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "b"));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "d"));
		tl += String.format("%s|", Utilidad.c(drtt(), "e"));
		tl += String.format("%s|", Utilidad.c(drtt(), "f"));
		tl += String.format("%s|", Utilidad.c(drtt(), "g"));
		tl += String.format("%s|", Utilidad.c(drtt(), "h"));
		;
		tl += "\n";
		t += tl;
		return t;
	}

	/* drtt(),8,8 */ /**
						 * imprime parte cup pc
						 * 
						 * @param tablerios
						 * @return
						 */
	public static String imprimircpu(String[][][] tablerios) {
		// TODO Auto-generated method stub

		String[][] mb = tablerios[0];
		String[][] mdisparo = tablerios[1];
		String[][] Cpub = tablerios[2];
		String[][] cpudisparo = tablerios[3];
		String t = "";
		String tl = "";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		int length = tl.length();
		for (int i = 0; i < mb.length; i++) {
			tl = "";
			/*
			 * tl += String.format("%s|", Utilidad.c(drtt(), i + 1)); for (int j = 0; j <
			 * mb[i].length; j++) { String casilla_mb = mb[i][j]; tl += String.format("%s|",
			 * Utilidad.c(drtt(), casilla_mb)); }
			 * 
			 * tl += String.format("%s|", Utilidad.c(drtt(), i + 1)); for (int j = 0; j <
			 * mdisparo[i].length; j++) { String casilla_mdisparo = mdisparo[i][j]; tl +=
			 * String.format("%s|", Utilidad.c(drtt(), casilla_mdisparo)); }
			 */

			tl += String.format("%s|", Utilidad.c(drtt(), i + 1));
			for (int j = 0; j < Cpub[i].length; j++) {
				String casilla_Cpub = Cpub[i][j];
				tl += String.format("%s|", Utilidad.c(drtt(), casilla_Cpub));
			}
			tl += String.format("%s|", Utilidad.c(10, ""));
			tl += String.format("%s|", Utilidad.c(drtt(), i + 1));
			for (int j = 0; j < cpudisparo[i].length; j++) {
				String casilla_cpudisparo = cpudisparo[i][j];
				tl += String.format("%s|", Utilidad.c(drtt(), casilla_cpudisparo));
			}

			length = tl.length();
			tl += "\n";

			tl += Utilidad.c(length, " ").replace(" ", "-");
			tl += "\n";

			t += tl;
		}

		tl += String.format("%s|", Utilidad.c(drtt(), " "));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "b"));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "d"));
		tl += String.format("%s|", Utilidad.c(drtt(), "e"));
		tl += String.format("%s|", Utilidad.c(drtt(), "f"));
		tl += String.format("%s|", Utilidad.c(drtt(), "g"));
		tl += String.format("%s|", Utilidad.c(drtt(), "h"));

		tl += String.format("%s|", Utilidad.c(drtt(), ""));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "b"));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "d"));
		tl += String.format("%s|", Utilidad.c(drtt(), "e"));
		tl += String.format("%s|", Utilidad.c(drtt(), "f"));
		tl += String.format("%s|", Utilidad.c(drtt(), "g"));
		tl += String.format("%s|", Utilidad.c(drtt(), "h"));
		;
		tl += "\n";
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "p"));
		tl += String.format("%s|", Utilidad.c(drtt(), "u"));
		tl += String.format("%s|", Utilidad.c(drtt(), " "));
		tl += String.format("%s|", Utilidad.c(drtt(), "m"));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "p"));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), " "));

		tl += String.format("%s|", Utilidad.c(10, ""));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "p"));
		tl += String.format("%s|", Utilidad.c(drtt(), "u"));
		tl += String.format("%s|", Utilidad.c(drtt(), " "));
		tl += String.format("%s|", Utilidad.c(drtt(), "m"));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "p"));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), " "));

		t += tl;
		return t;
	}

	/* drtt(),8,8 */ /**
						 * imprime parte cup pc
						 * 
						 * @param tablerios
						 * @return
						 */
	public static String imprimircpu_MI(String[][][] tablerios) {

		String[][] mb = tablerios[0];
		String[][] mdisparo = tablerios[1];
		String[][] Cpub = tablerios[2];
		String[][] cpudisparo = tablerios[3];
		String t = "";
		String tl = "";

		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		tl += "\n";
		int length = tl.length();
		for (int i = 0; i < mb.length; i++) {
			tl = "";

			/**
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 */
			tl += String.format("%s|", Utilidad.c(drtt(), i + 1));
			for (int j = 0; j < Cpub[i].length; j++) {
				String casilla_Cpub = Cpub[i][j];
				tl += String.format("%s|", Utilidad.c(drtt(), casilla_Cpub));
			}
			/**
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 * 
			 */
			length = tl.length();
			tl += "\n";

			tl += Utilidad.c(length, " ").replace(" ", "-");
			tl += "\n";

			t += tl;
		}

		tl += String.format("%s|", Utilidad.c(drtt(), " "));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "b"));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "d"));
		tl += String.format("%s|", Utilidad.c(drtt(), "e"));
		tl += String.format("%s|", Utilidad.c(drtt(), "f"));
		tl += String.format("%s|", Utilidad.c(drtt(), "g"));
		tl += String.format("%s|", Utilidad.c(drtt(), "h"));

		/*
		 * tl += String.format("%s|", Utilidad.c(10, "")); tl += String.format("%s|",
		 * Utilidad.c(drtt(), "")); tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		 * tl += String.format("%s|", Utilidad.c(drtt(), "b")); tl +=
		 * String.format("%s|", Utilidad.c(drtt(), "c")); tl += String.format("%s|",
		 * Utilidad.c(drtt(), "d")); tl += String.format("%s|", Utilidad.c(drtt(),
		 * "e")); tl += String.format("%s|", Utilidad.c(drtt(), "f")); tl +=
		 * String.format("%s|", Utilidad.c(drtt(), "g")); tl += String.format("%s|",
		 * Utilidad.c(drtt(), "h")); ;
		 */
		tl += "\n";
		tl += String.format("%s", Utilidad.c(drtt(), " "));
		tl += String.format("%s", Utilidad.c(drtt(), "m"));
		tl += String.format("%s", Utilidad.c(drtt(), "i"));
		tl += String.format("%s", Utilidad.c(drtt(), " "));
		tl += String.format("%s", Utilidad.c(drtt(), "m"));
		tl += String.format("%s", Utilidad.c(drtt(), "a"));
		tl += String.format("%s", Utilidad.c(drtt(), "p"));
		tl += String.format("%s", Utilidad.c(drtt(), "a"));
		tl += String.format("%s", Utilidad.c(drtt(), " "));

		t += tl;
		return t;
	}/* drtt(),8,8 */

	/**
	 * peid de tablero
	 * 
	 * @param tl
	 * @return
	 */
	public static String ddd(String tl) {
		tl += String.format("%s|", Utilidad.c(drtt(), " "));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "b"));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "d"));
		tl += String.format("%s|", Utilidad.c(drtt(), "e"));
		tl += String.format("%s|", Utilidad.c(drtt(), "f"));
		tl += String.format("%s|", Utilidad.c(drtt(), "g"));
		tl += String.format("%s|", Utilidad.c(drtt(), "h"));
		tl += String.format("%s", Utilidad.c(drtt(), ""));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "b"));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "d"));
		tl += String.format("%s|", Utilidad.c(drtt(), "e"));
		tl += String.format("%s|", Utilidad.c(drtt(), "f"));
		tl += String.format("%s|", Utilidad.c(drtt(), "g"));
		tl += String.format("%s|", Utilidad.c(drtt(), "h"));
		tl += String.format("%s|", Utilidad.c(10, ""));
		tl += String.format("%s|", Utilidad.c(drtt(), ""));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "b"));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "d"));
		tl += String.format("%s|", Utilidad.c(drtt(), "e"));
		tl += String.format("%s|", Utilidad.c(drtt(), "f"));
		tl += String.format("%s|", Utilidad.c(drtt(), "g"));
		tl += String.format("%s|", Utilidad.c(drtt(), "h"));
		tl += String.format("%s", Utilidad.c(drtt(), ""));
		tl += String.format("%s|", Utilidad.c(drtt(), "a"));
		tl += String.format("%s|", Utilidad.c(drtt(), "b"));
		tl += String.format("%s|", Utilidad.c(drtt(), "c"));
		tl += String.format("%s|", Utilidad.c(drtt(), "d"));
		tl += String.format("%s|", Utilidad.c(drtt(), "e"));
		tl += String.format("%s|", Utilidad.c(drtt(), "f"));
		tl += String.format("%s|", Utilidad.c(drtt(), "g"));
		tl += String.format("%s|", Utilidad.c(drtt(), "h"));
		tl += String.format("%s", Utilidad.c(drtt(), ""));
		tl += "\n";
		tl += String.format("%s", Utilidad.c(drtt(), " "));
		tl += String.format("%s", Utilidad.c(drtt(), "m"));
		tl += String.format("%s", Utilidad.c(drtt(), "i"));
		tl += String.format("%s", Utilidad.c(drtt(), " "));
		tl += String.format("%s", Utilidad.c(drtt(), "m"));
		tl += String.format("%s", Utilidad.c(drtt(), "a"));
		tl += String.format("%s", Utilidad.c(drtt(), "p"));
		tl += String.format("%s", Utilidad.c(drtt(), "a"));
		tl += String.format("%s", Utilidad.c(drtt(), " "));
		tl += String.format("%s", Utilidad.c(drtt(), " "));
		tl += String.format("%s", Utilidad.c(drtt(), ""));
		tl += String.format("%s", Utilidad.c(drtt(), " "));
		tl += String.format("%s", Utilidad.c(drtt(), "m"));
		tl += String.format("%s", Utilidad.c(drtt(), "i"));
		tl += String.format("%s", Utilidad.c(drtt(), " "));
		tl += String.format("%s", Utilidad.c(drtt(), "m"));
		tl += String.format("%s", Utilidad.c(drtt(), "a"));
		tl += String.format("%s", Utilidad.c(drtt(), "p"));
		tl += String.format("%s", Utilidad.c(drtt(), "a"));
		tl += String.format("%s", Utilidad.c(drtt(), " "));
		tl += String.format("%s", Utilidad.c(drtt(), " "));
		tl += String.format("%s|", Utilidad.c(10, ""));

		return tl;
	}

	/**
	 * 
	 * @return
	 */
	public static int drtt() {
		return 4;
	}

	/**
	 * 
	 * @param miflota
	 * @param length
	 */

	public static void cargar(String[][][] miflota, int length) {
		for (int i = 0; i < length; i++) {
			for (int j = 0; j < miflota[i].length; j++) {
				for (int j2 = 0; j2 < miflota[i][j].length; j2++) {
					miflota[i][j][j2] = ((i == 0) ? agua : ((i == 1) ? "" : ((i == 2) ? agua : ((i == 3) ? "" : ""))));
					// System.out.printf("%5s", miflota[i][j][j2]);🛥
				}

			}
		}
	}

}

```

## he trabajado con 
# sql
```sql
--tener una empresa de industrial del panadería que cuyo nombre es argelinos en zaragoza que necesita una base de datos para las operaciones logística que necesita guardarse en esa base. 
--y en la empresa realiza varios panes y poste y su jefe  nos ha pedido que asocien los empleados de líneas de producción con la recetas que preparan ellos y los test de producción y de gestión de ingredientes ,inventario y comprar ventas
-- y esta protegido por el protocolo  de eu , españal y por aljafaria  dato no he utilizado dni real sino hemos dejado el sistema  general  un numero  y da el formato dni de españa
--los ide  son numeros naturales 
 /*
 los campos ha registrar en las tablas son:
departamento que se guardan los siguientes datos . el código de departamento , el
nombre ,número de empleados que hay ,localización ,codigo de jefe.
en la tabla de empleados que trabajan en la empresa quieren guardarse los siguientes
datos : dni ,nombre ,apellidos ,número de teléfono ,e mal ,número de seguridad social
,dirección ,estudios realizados según sus puesto de trabajo de la empresa ,tipo de
contrato , tipo de trabajo desempeñado ,jefe ,bases de cotización ,irpf ,número de
seguridad social.
en la tabla de recetas se guardan :el código de receta ,nombre ,país de origen de la
receta ,tiempo de ejecución , números de ingrente,numero. de empleado arealizar,
pecio , número lotes, dia, dirrecion de envio
en la tabla de recetas se guardan :código, lotes, nombre, cantidad,precio unitario ,iva,
procedencia, dirección de procedencia, numero de inventario,tipo de almacenamiento
en la tabla de inventario se guardan : numero de entradas, numero de salida , precio
de lote, estado de inventarioala
en la tabla de ventas se guardan: código producto, precio, cantidad
en la tabla de compras se guardan: numero código de compra,numero dni del cliente ,
cantidad.
en la tabla de clientes se guardan: : dni ,nombre ,apellidos ,número de teléfono ,e mal
,número de seguridad social nombre de empresa
necesita las vista para ver la transacciones de los productos , ganancias y nuevos
empleado/as
 */
 CREATE TABLE DEPARTAMENTO
(
CÓDIGO_DE_DEPARTAMENTO NUMBER(6,0),
LOCALIZACIÓN VARCHAR(20),
NOMBRE VARCHAR(20),
DESCRIPCIÓN VARCHAR(20),
NUM_EMPLEADOS NUMBER(6,0),
NUM_SOCIAL NUMBER(6,0),
COTIZACIÓN NUMBER(6,0),
IRPF NUMBER(6,0)
);
ALTER TABLE DEPARTAMENTO
ADD CONSTRAINT PK_DEPARTAMENTO PRIMARY KEY (CÓDIGO_DE_DEPARTAMENTO);
CREATE TABLE EMPLEADO
(
NUM_SOCIAL NUMBER(6, 0)
, IRPF NUMBER(6, 0)
, SEG_SOCIA VARCHAR2(20 BYTE)
, NUM_SOCIA NUMBER(8, 0)
, DNI VARCHAR2(8 BYTE)
, NOMBRE VARCHAR2(20 BYTE)
, CÓDIGO_DE_DEPARTAMENTO NUMBER(6, 0) NOT NULL
, TELEFONO VARCHAR2(9 BYTE)
, EMAIL VARCHAR2(30 BYTE)
, DIRECCION VARCHAR2(30 BYTE)
, ESTUDIO VARCHAR2(30 BYTE)
, TIPO_CONTRATO VARCHAR2(30 BYTE)
);
ALTER TABLE EMPLEADO ADD CONSTRAINT PK_EMPLEADO PRIMARY KEY
(NUM_SOCIAL,Página 8 de 21
CÓDIGO_DE_DEPARTAMENTO
);
ALTER TABLE EMPLEADO ADD
ADD CONSTRAINT FK_CÓDIGO_DE_DEPARTAMENTO
FOREIGN KEY (CÓDIGO_DE_DEPARTAMENTO) REFERENCES DEPARTAMENTO(PERSONID);
CREATE TABLE INVENTARIO
(
NUMERO_ENTRADAS NUMBER(6, 0) ,
NUMERO_SALIDAS NUMBER(6, 0) ,
PRECIO_LOTE NUMBER(8, 2) ,
INVENTARIOLA NUMBER(8, 0) ,
IVA NUMBER(3, 2) ,
PROCECIA VARCHAR2(30),
DIRECCION_PTOCEDECIA VARCHAR2(30),
NUM_INVENTARIO NUMBER(6, 0),
TIPO_ALMACENAMIETO VARCHAR2(30)
);
ALTER TABLE INVENTARIO ADD CONSTRAINT PK_INVENTARIO PRIMARY KEY
(NUMERO_SALIDAS, NUMERO_ENTRADAS, NUM_INVENTARIO );
CREATE TABLE INGREDIENTE
(
COD INTEGER ,
LOTES INTEGER,
NOMBRE VARCHAR2(15),
CANTIDAD NUMBER(8,2),
IVA NUMBER(2,2),
PROCEDIA VARCHAR2(30),
DIRECCIÓN_PTOCEDECIA VARCHAR2(30),
NUM_INVENTARIO INTEGER ,
TIPO_ALMACENAMIETO VARCHAR2(30)
);Página 9 de 21
ALTER TABLE INGREDIENTE ADD CONSTRAINT PK_INGREDIENTE PRIMARY KEY (COD, LOTES);
CREATE TABLE INGREDI_INVEN_TABLA_RELACION
(
COD INTEGER ,
LOTES INTEGER,
NUMERO_ENTRADAS NUMBER(6, 0) ,
NUMERO_SALIDAS NUMBER(6, 0) ,
NUM_INVENTARIO NUMBER(6, 0)
);
ALTER TABLE INGREDI_INVEN_TABLA_RELACION
MODIFY (COD NOT NULL);
ALTER TABLE INGREDI_INVEN_TABLA_RELACION
MODIFY (LOTES NOT NULL);
ALTER TABLE INGREDI_INVEN_TABLA_RELACION
MODIFY (NUMERO_ENTRADAS NOT NULL);
ALTER TABLE INGREDI_INVEN_TABLA_RELACION
MODIFY (NUMERO_SALIDAS NOT NULL);
ALTER TABLE INGREDI_INVEN_TABLA_RELACION
MODIFY (NUM_INVENTARIO NOT NULL);
ALTER TABLE INGREDI_INVEN_TABLA_RELACION
ADD CONSTRAINT INGREDI_INVEN_TABLA_RELACI_PK PRIMARY KEY
(
COD
, LOTES
, NUMERO_ENTRADASPágina 10 de 21
, NUM_INVENTARIO
, NUMERO_SALIDAS
)
ALTER TABLE INGREDI_INVEN_TABLA_RELACION
ADD CONSTRAINT INGREDI_INVEN_TABLA_RELAC_FK1 FOREIGN KEY
(
NUMERO_SALIDAS
, NUMERO_ENTRADAS
, NUM_INVENTARIO
)
REFERENCES INVENTARIO
(
NUMERO_SALIDAS
, NUMERO_ENTRADAS
, NUM_INVENTARIO
)
ENABLE;
ALTER TABLE INGREDI_INVEN_TABLA_RELACION
ADD CONSTRAINT INGREDI_INVEN_TABLA_RELAC_FK2 FOREIGN KEY
(
COD
, LOTES
)
REFERENCES INGREDIENTE
(
COD
, LOTES
)
CREATE TABLE CLIENTE
(
DNI VARCHAR(8),Página 11 de 21
NOMBRE_CLIENTE VARCHAR(20)
);
ALTER TABLE CLIENTE ADD CONSTRAINT PK_CLIENTE PRIMARY KEY (DNI , NOMBRE_CLIENTE );
CREATE TABLE COMPRAS
( COD_COMPRA NUMBER(16,0), NOMBRE VARCHAR(20),CANTIDAD FLOAT
);
ALTER TABLE COMPRAS ADD CONSTRAINT PK_COMPRAS PRIMARY KEY (COD_COMPRA );
CREATE TABLE VENTAS
(
COD_VENTAS NUMBER(16,0),
NOMBRE VARCHAR(20),
CANTIDAD FLOAT,
DNI VARCHAR(8),
NOMBRE_CLIENTE VARCHAR(20)
);
ALTER TABLE VENTAS ADD CONSTRAINT PK_COD_VENTAS PRIMARY KEY (COD_VENTAS );
CREATE TABLE RECETAS
(
CODIGO_PRODUCTO NUMBER(9,0),
PRECIO FLOAT,
NOMBRE VARCHAR2(20),
CANTIDAD INT,
IVA DECIMAL,
PROCEDECIA VARCHAR2(20),
DIRRECIO_PROCENCIA VARCHAR2(20),
NUM_DEINVETARIO INT,
TIPO_ALMACENAMIENTO VARCHAR2(20),
COD_COMPRA NUMBER(16,0),
COD_VENTAS NUMBER(16, 0),
CÓDIGO_DE_DEPARTAMENTO NUMBER(6,0)
);Página 12 de 21
ALTER TABLE RECETAS
ADD (COD_INGREDIEN VARCHAR2(20) );
ALTER TABLE RECETAS ADD CONSTRAINT PK_RECETAS PRIMARY KEY (CODIGO_PRODUCTO );
ALTER TABLE RECETAS ADD CONSTRAINT FK_COMPRAS_RECETAS FOREIGN KEY
(COD_COMPRA) REFERENCES COMPRAS(COD_COMPRA);
ALTER TABLE RECETAS ADD CONSTRAINT FK_VENTAS_RECETAS FOREIGN KEY (COD_VENTAS)
REFERENCES VENTAS(COD_VENTAS);
ALTER TABLE RECETAS ADD CONSTRAINT FK_DEPARTAMENTO_RECETAS FOREIGN KEY
(CÓDIGO_DE_DEPARTAMENTO) REFERENCES
DEPARTAMENTO(CÓDIGO_DE_DEPARTAMENTO);
ALTER TABLE COMPRAS MODIFY (CANTIDAD NUMBER(6,2) );
ALTER TABLE EMPLEADO
ADD (FECHA DATE );
ALTER TABLE COMPRAS
ADD (FECHA DATE );
ALTER TABLE VENTAS ADD (FECHA DATE );
UPDATE VENTAS SET VENTAS.FECHA = SYSDATE;
```
