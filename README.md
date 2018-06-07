# HelloWorld

/** 洗牌 */
package Test;

/**
 * @author 啵
 * @version 创建时间：2018年5月22日 下午2:37:44 洗牌
 */
public class shuffleDemo {

	public static void main(String[] args) {
		String[] cardColors = { "黑桃", "红心", "梅花", "方块" };
		String[] cardValues = { "A", "2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K" };
		final int N = 52;
		int[] cards = new int[N];
		// 初始化52张牌
		for (int i = 0; i < cards.length; i++) {
			cards[i] = i;
		}
		// 洗牌前
		System.out.println("洗牌前：");
		for (int i = 0; i < cards.length; i++) {
			// System.out.print(cards[i]);
			System.out.printf("%s-%s", cardColors[cards[i] / 13], cardValues[cards[i] % 13]);
			if ((i + 1) % 13 == 0) {
				System.out.println();
			} else {
				System.out.print("  ");
			}
		}
		// 洗牌
		for (int i = 0; i < cards.length; i++) {
			int Newcard = (int) (Math.random() * N);
			int temp = cards[i];
			cards[i] = cards[Newcard];
			cards[Newcard] = temp;
		}
		// 洗牌后
		System.out.println("洗牌后：");
		for (int i = 0; i < cards.length; i++) {
			System.out.printf("%s-%s", cardColors[cards[i] / 13], cardValues[cards[i] % 13]);
			// System.out.print(cards[i]);
			if ((i + 1) % 13 == 0) {
				System.out.println();
			} else {
				System.out.print("  ");
			}
		}
	}

}

