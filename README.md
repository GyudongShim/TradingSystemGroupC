#### TradingSystemGroupC
---

### 해야 할 일 

1. StockDriverInterface 설계 및 refine
    - Login(string id, string passwrd) : bool
    - Buy(long tickerCode, double amount) : double
    - Sell(long tickerCode, double shareCount) : double
    - GetPrice(long tickerCode) : double
    - BuyNiceTiming(long tickerCode, double totalMoney) : long
    - SellNiceTiming(long tickerCode, long shareCount) : long
      
2. StockBrokerDriver interface 확정
    - Login(string id, string passwrd) : bool
    - Buy(long tickerCode, double amount) : double
    - Sell(long tickerCode, double abount) : double
    - GetPrice(long tickerCode) : double
      
3. AutoTrandingSystem 구현
   Sequence diagram 작성
   

----
### 참고

주어진 API
   A) Kiwer
	void login(string ID, string password) {
		cout << ID << " login success\n";
	}

	void buy(string stockCode, int count, int price) {
		cout << stockCode << " : Buy stock ( " << price << " * " << count << ")\n";
	}

	void sell(string stockCode, int count, int price) {
		cout << stockCode << " : Sell stock ( " << price << " * " << count << ")\n";
	}

	int currentPrice(string stockCode) {
		srand(time(NULL));
		int ret = rand() % 10 * 100 + 5000;
		return ret;
	}
};

  B) Nemo
 void certification(string ID, string pass) {
		cout << "[NEMO]" << ID << " login GOOD\n";
	}

	void purchasingStock(string stockCode, int price, int count) {
		cout << "[NEMO]" << stockCode << " buy stock ( price : " << price << " ) * ( count : " << count << ")\n";
	}

	void sellingStock(string stockCode, int price, int count) {
		cout << "[NEMO]" << stockCode << " sell stock ( price : " << price << " ) * ( count : " << count << ")\n";
	}

	int getMarketPrice(string stockCode, int minute) {
		//minute ms초 이후 구매가 되는 방식 (최소 1 ms)
		if (minute <= 0) minute = 1;
		Sleep(minute);
		srand(time(NULL));
		int ret = rand() % 10 * 100 + 5000;
		return ret;
	}

