0.通过myconfig.json配置债券基础信息路径，评估日，基础现金流路径，以及利率曲线的压力参数
1.cashflow_cal,interest_curve_cal分别用于计算现金流和生成压力情景下的利率曲线
1.1cashflow返回result_df, principal_result_df, coupon_result_df,分别是总现金流，本金现金流和票息现金流
1.2interest_curve_cal返回monthly_df,包含基础情景，利率下，利率上三条折现率曲线
2.mc_cal根据现金流和折现率曲线计算pv值（pv,pv_down,pv_up)导出excel表,beautify用于美化导出的excel表
3.详细参数配置信息参考各py文件的注释


git操作指南：
1.新建本地仓库并推送到github
echo "# 仓库名" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/你的用户名/仓库名.git
git push -u origin main

2.已有本地仓库：
git remote add origin https://github.com/你的用户名/仓库名.git
git branch -M main  # 确保分支名为 main（或根据 GitHub 提示修改）
git push -u origin main


3.GitHub 已禁用密码认证，当你使用 HTTPS 协议克隆或推送代码时，必须提供：
个人访问令牌（PAT）：替代密码的认证方式。
SSH 密钥：通过 SSH 协议进行认证（推荐）。
所以已经将认证方式修改至ssh密钥：（已经生成并配置，无需再次操作3.1，3.2）
3.1ssh-keygen -t ed25519 -C "your_email@example.com"
# 按提示完成生成（直接回车使用默认路径和密码）
3.2cat ~/.ssh/id_ed25519.pub  之后复制密钥内容粘贴至GitHub  

3.3修改远程仓库地址：
# 将 HTTPS 地址替换为 SSH 地址
git remote set-url origin git@github.com:MarioMHFeng/interest_rate_mc_cal.git

# 验证 SSH 连接
ssh -T git@github.com
# 应显示：Hi MarioMHFeng! You've successfully authenticated...


之后正常push
