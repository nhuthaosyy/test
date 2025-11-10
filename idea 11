1. Thiết lập giao diện
Giao diện chính của trò chơi mà một ô vuông lớn bao gồm 81 ô vuông nhỏ và chia thành 9 hàng và 9 cột, bên cạnh đó cũng chia thành 9 ô vuông nhỏ hơn và mỗi ô vuông cũng chưa 9 ô vuông nhỏ gồm 3 hàng và 3 cột, như hình dưới:



Để làm được giao diện như thế này, ta chỉ cần tạo ra ma trận JButton[9][9], và cần setBorfer cho từng button để có được giao diện như trên.

	public Container init() {
		Container cn = this.getContentPane();
		pn2 = new JPanel();
		pn2.setLayout(new FlowLayout());
		time_lb = new JLabel("00:00:00:00");
		sls_lb = new JLabel("Có thể sai 3 lần");
		
		newGame_bt = new JButton("New Game");
		newGame_bt.addActionListener(this);
		highScore_bt = new JButton("High Score");
		highScore_bt.addActionListener(this);
		
		lv.addItem("Dễ");
		lv.addItem("Trung bình");
		lv.addItem("Khó");
		lv.setSelectedIndex(LV);
		
		
		pn2.add(newGame_bt);
		pn2.add(lv);
		pn2.add(time_lb);
		pn2.add(sls_lb);
		pn2.add(highScore_bt);
		cn.add(pn2, "North");
		
		pn = new JPanel();
		pn.setLayout(new GridLayout(9, 9));
		for (int i = 0; i < 9; i++)
			for (int j = 0; j < 9; j++) {
				bt[i][j] = new JButton();
				bt[i][j].addActionListener(this);
				bt[i][j].addKeyListener(this);
				bt[i][j].setActionCommand(i + " " + j);
				bt[i][j].setBackground(Color.white);
				bt[i][j].setFont(new Font("UTM Micra", 1, 30));
				bt[i][j].setForeground(Color.black);
				pn.add(bt[i][j]);
			}
		for (int i = 0; i < 9; i += 3)
			for (int j = 0; j < 9; j += 3) {
				bt[i][j].setBorder(BorderFactory.createMatteBorder(3,3,1,1, Color.black));
				bt[i][j + 2].setBorder(BorderFactory.createMatteBorder(3,1,1,3, Color.black));
				bt[i + 2][j + 2].setBorder(BorderFactory.createMatteBorder(1,1,3,3, Color.black));
				bt[i + 2][j].setBorder(BorderFactory.createMatteBorder(1,3,3,1, Color.black));
				bt[i][j + 1].setBorder(BorderFactory.createMatteBorder(3,1,1,1, Color.black));
				bt[i + 1][j + 2].setBorder(BorderFactory.createMatteBorder(1,1,1,3, Color.black));
				bt[i + 2][j + 1].setBorder(BorderFactory.createMatteBorder(1,1,3,1, Color.black));
				bt[i + 1][j].setBorder(BorderFactory.createMatteBorder(1,3,1,1, Color.black));
				bt[i + 1][j + 1].setBorder(BorderFactory.createMatteBorder(1,1,1,1, Color.black));
			}
		
		cn.add(pn);
		this.setVisible(true);
		this.setSize(700, 700);
		this.setLocationRelativeTo(null);
		this.setResizable(false);
		try {
			creatMatrix();
		} catch (FileNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		timer = new Timer(10, new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				time_lb.setText(next(time_lb));
			}
		});
		return cn;
	}
