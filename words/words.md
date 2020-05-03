<div class="section">
    <div>
    	<iframe id="splash" width="960" height="480" src="banners/splash.html"></iframe>
        <div style="top: 70px;font-size: 75px;font-weight: bold;">
        	次に何が起こるのか?
       	</div>
		<div style="font-weight: 500;top: 140px;left: 10px;font-size: 29px;">
			シミュレーションで分かる新型コロナウイルス感染症 (COVID-19) の未来
		</div>
		<div style="font-weight: 100;top: 189px;left: 10px;font-size: 19px;line-height: 21px;">
			<b>
				🕐 所要時間 30分
				&nbsp;&middot;&nbsp;
			</b>
			<a href="https://scholar.google.com/citations?user=_wHMGkUAAAAJ&amp;hl=en">Marcel Salathé</a>
			(疫学者)
			&
			<a href="https://ncase.me/">Nicky Case</a>
			(アート/コード)
      &
      <a href="http://eed3si9n.com/">Eugene Yokota</a>
      (和訳)
		</div>
	</div>
</div>

「真に恐れるべきは恐怖そのものである」とは馬鹿げた忠告だ。

勿論トイレットペーパーの買いだめはするべきでは無い。しかし、政策立案者が恐怖そのものを恐れると、「集団パニック」を予防せんと彼らは真の危険を過小評価してしまう。恐怖が問題なのではなく、我々がその恐怖のエネルギーをどこに向けるかが問題だ。恐怖は今の脅威に対処し、将来の危険に備えるエネルギーを与えてくれる。

正直の所、私たち (疫学者 Marcel + アート/コード担当の Nicky) は心配で仕方がない。あなたも心配だと思う。私たちは恐怖の力をこの**いじれるシミュレーション**を作ることに向けた。あなたが恐怖の力を以下のことを理解することに向けて欲しいと思ったからだ:

* **過去数ヶ月のこと** (疫学入門、SEIR モデル、R & R<sub>0</sub>)
* **次の数ヶ月のこと** (ロックダウン、コンタクト・トレーシング、マスク)
* **次の数年のこと** (免疫の喪失? ワクチンが無い場合?)

このガイド (2020年5月1日に公開された。脚注をクリック!→[^timestamp]) はあなたに希望を与え、恐怖をもたらすことを分かった上で書いている。**メンタルヘルスと金銭的な健全性の両方を保護する形**で COVID-19 をやっつけるには、プランを練るための楽観論と、バックアッププランを練るための悲観論を必要とする。Gladys Bronwyn Stern を引用すると、「楽観論者は飛行機を発明し、悲観論者はパラシュートを発明する」。

[^timestamp]: これらの脚注には、原典、リンク、ボーナスコメントなどが書かれる。

    **This guide was published on May 1st, 2020.** Many details will become outdated, but we're confident this guide will cover 95% of possible futures, and that Epidemiology 101 will remain forever useful.

シートベルトを着用してください。機体の揺れが予想されます。

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>過去数ヶ月のこと</div>
    </div>
</div>

パイロットはフライト・シミュレーターを使って飛行機を墜落させない方法を学ぶ。

**疫学者はエピデミック・シミュレーターを使って人類を墜落させない方法を学ぶ。**

まずは、非常にシンプルな「感染症フライト・シミュレーター」を作ってみよう! このシミュレーションでは <icon i></icon> **伝染性のある人々**が <icon s></icon> **感受性のある人々**をより多くの <icon i></icon> 伝染性のある人々へ変えていく:

![](pics/spread.png)

COVID-19 アウトブレイクの**初期**には、ウイルスは**平均して** <icon i></icon> から <icon s></icon> へと 4日おきにジャンプすると推定されている。[^serial_interval] (当然これには色々と差異がある。)

[^serial_interval]: “The mean [serial] interval was 3.96 days (95% CI 3.53–4.39 days)”. [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article) (Disclaimer: Early release articles are not considered as final versions)

「4日おきに 2倍」だけシミュレートして**他の要素を無視すると**、全人口の 0.001% <icon i></icon> からスタートしてどうなるだろうか?

**「スタート」をクリックしてシミュレーションをプレイしてみよう! 別の設定でリプレイしてみることもできる:** (専門家への注意: [^caveats])

[^caveats]: **これらのシミュレーションは教育目的のために非常に簡易化してある。**
    
    One simplification: When you tell this simulation "Infect 1 new person every X days", it's actually increasing # of infected by 1/X each day. Same for future settings in these simulations – "Recover every X days" is actually reducing # of infected by 1/X each day.
    
    Those *aren't* exactly the same, but it's close enough, and for educational purposes it's less opaque than setting the transmission/recovery rates directly.

<div class="sim">
		<iframe src="sim?stage=epi-1" width="800" height="540"></iframe>
</div>

これは、**指数関数的成長曲線**だ。初めは小さく、突然爆発的に伸びる。「ただのインフルだよ」から「確かにインフルで都市部に集団墓地が作られることは無いな」への変化だ。

![](pics/exponential.png)

しかし、このシミュレーションは間違っている。指数関数的成長は、永遠に続くことはできない。他の人が既にウイルスを持っていればそれ以上ウイルスは伝搬することは無いからだ:

![](pics/susceptibles.png)

<icon i></icon> の人がいればいるほどより速く <icon s></icon> の人は <icon i></icon> になるが、**<icon s></icon> の人が少なくなるほど、より遅く <icon s></icon> の人は <icon i></icon> になる**。

このことはエピデミックの成長にどう影響があるだろうか? 確かめてみよう:

<div class="sim">
		<iframe src="sim?stage=epi-2" width="800" height="540"></iframe>
</div>

これは「S字の」**ロジスティック成長曲線**と呼ばれる。初めは小さく、爆発して、また遅くなる。

しかし、このシミュレーションは**それでも**間違っている。<icon i></icon> **伝染性のある人**がいずれ 1) 回復する 2) 肺に後遺症を持って「回復」する 3) 死亡するなどして伝染性が無くなることを計算に入れていない。

便宜性のため、全ての <icon i></icon> **伝染性のある人**は <icon r></icon> **回復した人**になることにしよう。(現実では、死んでしまう人もいることを覚えておいてほしい。) <icon r></icon> の人は再び感染することはできなくて、**とりあえず**一生免疫を持つと仮定しよう。

COVID-19 では、<icon i></icon> **伝染性**は平均して10日続くと推定されている。[^infectiousness] そのため、10日経つ前に回復する人もいれば、10日経ってから回復する人もいるということだ。**<icon i></icon> が 100% から始めるたシミュレーションは以下のようになる:**

[^infectiousness]: “The median communicable period \[...\] was 9.5 days.” [Hu, Z., Song, C., Xu, C. et al](https://link.springer.com/article/10.1007/s11427-020-1661-4) Yes, we know "median" is not the same as "average". For simplified educational purposes, close enough.

<div class="sim">
		<iframe src="sim?stage=epi-3" width="800" height="540"></iframe>
</div>

これは指数関数的成長の逆で、**指数関数的減衰曲線**だ。

次に、S字のロジスティック成長曲線と回復を合わせるとどうなるだろうか?

![](pics/graphs_q.png)

確かめてみよう。

<b style='color:#ff4040'>赤の曲線</b>は、**現在**の患者数 <icon i></icon> で、    
<b style='color:#999999'>グレーの曲線</b>は**総患者数** (現在 + 回復済み <icon r></icon>)　で、<icon i></icon> が 0.001% から始める:

<div class="sim">
		<iframe src="sim?stage=epi-4" width="800" height="540"></iframe>
</div>

**これ**が有名な曲線の由来だ! ベル曲線でもないし、対数正規曲線も違う。名前はまだ無い。しかし、あなたはこれを平らにしようと懇願する人を既に何度も見たことがあるだろう。

<icon s></icon>**S**usceptible (感受性) <icon i></icon>**I**nfectious (伝染性) <icon r></icon>**R**ecovered (回復) の頭文字を取ってこれを **SIR モデル** [^sir] と呼ぶ。これは疫学入門で 2番目に大切なことだ:

[^sir]: For more technical explanations of the SIR Model, see [the Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-sir.html#) and [Wikipedia](https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology#The_SIR_model)

![](pics/sir.png)

**注意: 政策の計画に使われるシミュレーションはこれよりもっと、もっと高度なものだ!** しかし、この SIRモデルにニュアンスが欠けるとしても、分かっている知見を説明することは可能だ。

やっぱりもう1つのニュアンスを追加しよう。<icon s></icon> の人が <icon i></icon> になる前に、その人たちは <icon e></icon> **曝露**した人になる。これは、ウイルスを保菌するが、他の人にはまだうつせない状態で、**感染した**がまだ**伝染性が無い**状態だ。

![](pics/seir.png)

**曝露** (Exposed) の "E" を取って、これは **SEIR モデル**[^seir]と呼ばれる。日常的な「さらされる」という意味だとウイルスを持っているか、持っていないか両方に取れるかもしれない。用語としての「曝露」は、確実にウイルスを保菌した状態だ。

[^seir]: For more technical explanations of the SEIR Model, see [the Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-seir.html) and [Wikipedia](https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology#The_SEIR_model)

COVID-19 では、<icon e></icon> 「感染したが、伝染性は無い」状態が**平均して** 3日続くと推定されている。[^latent] これをシミュレーションに追加するとどうなるだろう?

[^latent]: “Assuming an incubation period distribution of mean 5.2 days from a separate study of early COVID-19 cases, we inferred that infectiousness started from 2.3 days (95% CI, 0.8–3.0 days) before symptom onset” (translation: Assuming symptoms start at 5 days, infectiousness starts 2 days before = Infectiousness starts at 3 days) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)

<b style='color:#ff4040'>赤 <b style='color:#FF9393'>+ ピンク</b> の曲線</b>は**現在**の患者数 (伝染性 <icon i></icon> + 曝露 <icon e></icon>) で、    
<b style='color:#888'>グレーの曲線</b>は**総患者数** (現在 + 回復済み <icon r></icon>) だ:

<div class="sim">
		<iframe src="sim?stage=epi-5" width="800" height="540"></iframe>
</div>

あまり変わらない! <icon e></icon> 曝露された状態がどれだけ続くかは <icon e></icon>-対-<icon i></icon> 率と、**いつ**現在の患者数がピークに達するかを変化させる... しかし、ピークの**高さ**と最終的な総患者数は変わらない。

何故かって? その理由は疫学入門で1番大切なことだ:

![](pics/r.png)

これは再生産数 (reproduction number) の略だ。これは <icon i></icon> の人が回復 (もしくは死亡) する前に何人伝染させるかの**平均**だ。

![](pics/r2.png)

**R** はアウトブレイクの過程で、私たちが免疫を得たり、介入を行うことによって変化し続けていく。

基本再生産数 **R<sub>0</sub>** (R-nought、アーナットと読まれる) は、R の初期値で**免疫を得たり、介入を行う前**の数値だ。R<sub>0</sub> はウイルスそのものの力を反映するが、それでも場所によって変化する。例えば、R<sub>0</sub> は田舎よりも人口密度の高い都市部で高い傾向にある。

(多くのニュース記事や、論文でさえこの R と R<sub>0</sub> が混同されている。科学用語は悪だ。)

季節性インフルエンザの R<sub>0</sub> は約 1.28[^r0_flu]だ。そのため、インフルエンザのアウトブレイク**初め**は、<icon i></icon> の人は**平均して** 1.28人に伝染させる。(これが整数じゃないことに違和感があるならば、平均すると母親は 2.4人の子供を持つことを考えてみて欲しい。だからといって、半分になった子供が走り回っている訳ではない。)

[^r0_flu]: “The median R value for seasonal influenza was 1.28 (IQR: 1.19–1.37)” [Biggerstaff, M., Cauchemez, S., Reed, C. et al.](https://bmcinfectdis.biomedcentral.com/articles/10.1186/1471-2334-14-480)

COVID-19 の R<sub>0</sub> は約 2.2 だと推定されていて[^r0_covid]、まだ最終的な結果は出ていないが武漢では 5.7(!) であったという研究が出ている。[^r0_wuhan]

[^r0_covid]: “We estimated the basic reproduction number R0 of 2019-nCoV to be around 2.2 (90% high density interval: 1.4–3.8)” [Riou J, Althaus CL.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7001239/)

[^r0_wuhan]: “we calculated a median R0 value of 5.7 (95% CI 3.8–8.9)” [Sanche S, Lin YT, Xu C, Romero-Severson E, Hengartner N, Ke R.](https://wwwnc.cdc.gov/eid/article/26/7/20-0282_article)

私たちのシミュレーションでは、**初期には平均して** 1人の <icon i></icon> は 10日の間、誰かを 4日毎に伝染させる。「4日」は「10日」に 2.5回入る。そのため、**初期には平均して** 1人の <icon i></icon> は 2.5人の他人に伝染させる。つまり、 R<sub>0</sub> = 2.5 となる。 (注意:[^r0_caveats_sim])

[^r0_caveats_sim]: これは伝染期間中等しく伝染性を持つことを仮定する。教育目的のための簡易化だ。

**R<sub>0</sub> 計算機をいじってみて、R<sub>0</sub> が回復に要する期間と新しい伝染に要する期間に依存することを確かめてみよう:**

<div class="sim">
		<iframe src="sim?stage=epi-6a&format=calc" width="285" height="255"></iframe>
</div>

しかし、<icon s></icon> が少なければ少ないほど <icon s></icon> が <icon i></icon> になるのは**遅く**なるのを思い出してほしい。**現在**の再生産数 (R) は、基本再生産数 (R<sub>0</sub>) だけではなく、何人が <icon s></icon> 感受性のある人じゃ無くなったかにも依存するということだ。(例えば、回復して自然免疫を獲得することで感受性が無くなる。)

<div class="sim">
		<iframe src="sim?stage=epi-6b&format=calc" width="285" height="390"></iframe>
</div>

十分な人に免疫があると、R < 1 となりウイルスを封じ込めたことになる! これは**集団免疫**と呼ばれる。インフルエンザでは、集団免疫は**ワクチンによって**達成させられる。人々に感染させることをで「自然な集団免疫」を得ようとするのは**酷い**考えだ。(しかし、あなたが考えているのとは違う理由だ! これは後ほど説明する。)

SEIR モデルをいじってみよう。今回は R<sub>0</sub>、R の変化、および集団免疫の閾値を表示する:

<div class="sim">
		<iframe src="sim?stage=epi-7" width="800" height="540"></iframe>
</div>

**注意: 総患者数は集団免疫で止まらず、伸び続けてしまう!** これを「オーバーシュート」と言う。現在患者数がピークに達する時**ちょうど**に閾値をまたいでしまう。(これはどう設定を変えても起こってしまう。試してみよう!)

これは集団免疫閾値よりも多くの非-<icon s></icon> がいる時 R < 1 を得られるためだ。R < 1 になると新しい患者数は成長を止め、ピークとなる。

**もしこのガイドから 1つだけ学ぶとしたら、以下の事を学んでほしい**。これは非常に複雑な図式なので、じっくり時間をさいて考えてほしい:

![](pics/r3.png)

**これは COVID-19 を止めるためには、全ての伝染を止める必要も、ほぼ全ての伝染を止める必要もないことを示している!**

これはパラドックスだ。COVID-19 は非常に伝染性が高い。しかし、封じ込めるには「たった」60% の伝染を止めるだけでいい。60%?! これが学校の成績ならば D- だ。しかし、もし R<sub>0</sub> = 2.5 ならば、それを 61% オフにすると R = 0.975 となり、これは R < 1 でウイルスを封じ込めることができた! (正確な公式:[^exact_formula])

[^exact_formula]: Remember R = R<sub>0</sub> * the ratio of transmissions still allowed. Remember also that ratio of transmissions allowed = 1 - ratio of transmissions *stopped*.
    
    Therefore, to get R < 1, you need to get R<sub>0</sub> * TransmissionsAllowed < 1. 
    
    Therefore, TransmissionsAllowed < 1/R<sub>0</sub>
    
    Therefore, 1 - TransmissionsStopped < 1/R<sub>0</sub>
    
    Therefore, TransmissionsStopped > 1 - 1/R<sub>0</sub>
    
    Therefore, you need to stop more than **1 - 1/R<sub>0</sub>** of transmissions to get R < 1 and contain the virus!

![](pics/r4.png)

(R<sub>0</sub> その他の数値が高すぎるか低すぎると思うならば、前提を疑うのは良いことだ! このガイドの最後に「サンドボックス・モード」があってそこで自分の数値を入れてどうなるかをシミュレートできるようになっている。)

あなたが聞いたことのある**全て**の COVID-19 対策、手洗い、社会的/物理的距離、ロックダウン、自己隔離、コンタクト・トレーシング、検疫、マスク、「集団免疫」などこれらは**全て**同じことを目指している。

R < 1 を得ることだ。

「エピデミック・フライト・シミュレーター」を使って以下を考えてみよう: **メンタルヘルスと金銭的な健全性の両方を保護する形**で R < 1 を達成するにはどうすればいいだろうか?

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>次の数ヶ月のこと</div>
    </div>
</div>

次の数ヶ月はより悪い事態にある可能性もあった。以下は、私たちが回避した並行世界だ:

### シナリオ 0: 一切何もしない

COVID-19 に感染した 20人に 1人は ICU (集中治療室) へ行く必要がある。[^icu_covid] アメリカのような裕福な国では人口 3400人に対して 1つの ICU ベッドがある。[^icu_us] つまり、アメリカは 3400 人のうち 20人のみが**同時**に感染するのを対処することができ、これは人口の 0.6% だ。

[^icu_covid]: ["Percentage of COVID-19 cases in the United States from February 12 to March 16, 2020 that required intensive care unit (ICU) admission, by age group"](https://www.statista.com/statistics/1105420/covid-icu-admission-rates-us-by-age-group/). Between 4.9% to 11.5% of *all* COVID-19 cases required ICU. Generously picking the lower range, that's 5% or 1 in 20. Note that this total is specific to the US's age structure, and will be higher in countries with older populations, lower in countries with younger populations.

[^icu_us]: “Number of ICU beds = 96,596”. From [the Society of Critical Care Medicine](https://sccm.org/Blog/March-2020/United-States-Resource-Availability-for-COVID-19) USA Population was 328,200,000 in 2019. 96,596 out of 328,200,000 = roughly 1 in 3400. 

もしも、このキャパシティーを**3倍以上に上げて** 2% にしたとしても、一切何もしない場合はこうなる:

<div class="sim">
		<iframe src="sim?stage=int-1&format=lines" width="800" height="540"></iframe>
</div>

良くない結果だ。

これが[インペリアル・カレッジ・ロンドンの3月16日の報告書](http://www.imperial.ac.uk/mrc-global-infectious-disease-analysis/covid-19/report-9-impact-of-npis-on-covid-19/)での知見だ: 何もしないと、ICU が足りなくなり、人口の 80% が感染する。
(総患者数は集団免疫をオーバーシュートすることを思い出してほしい)

感染者の 0.5% が死亡したとしても (ICU が無い状態では寛大な前提だ) 3億人の人口を持つアメリカのような大きい国では、3億人の 80% の 0.5% = 120万人の死亡者を出すことになる... **もしも**一切何もしなければ。

(ニュースやソーシャルメディアでは「もしも一切何もしなければ」を抜いて「80% が感染する」だけを報道した。恐怖は理解では無くクリック数にのみ注がれた。やれやれ。)

### シナリオ 1: 曲線を平らにせよ / 集団免疫

「曲線を平らにせよ」(flatten the curve) という計画は全ての公衆衛生団体によって売り込まれ、イギリスの「集団免疫」計画は全世界の非難を浴びた。これらは同じ計画だ。イギリスのコミュニケーションが下手くそだっただけだ。[^yong]

[^yong]: “He says that the actual goal is the same as that of other countries: flatten the curve by staggering the onset of infections. As a consequence, the nation may achieve herd immunity; it’s a side effect, not an aim. [...] The government’s actual coronavirus action plan, available online, doesn’t mention herd immunity at all.”
    
    From a [The Atlantic article by Ed Yong](https://www.theatlantic.com/health/archive/2020/03/coronavirus-pandemic-herd-immunity-uk-boris-johnson/608065/)

両方の計画とも、文字通り致命的な欠陥があった。

まずは「曲線を平らにする」ための主な 2つの方法を見ていこう: 手洗いと物理的距離戦略だ。

手洗いの増加は、高収入な国においてはインフルエンザや風邪を ~25% 減少させ[^handwashing]、ロンドンでの都市規模のロックダウンは接触を ~70% 減少させた[^london]。そのため、手洗いは R を最高で 25%、距離戦略は R を最高で 70% 減少させると仮定しよう:

[^handwashing]: “All eight eligible studies reported that handwashing lowered risks of respiratory infection, with risk reductions ranging from 6% to 44% [pooled value 24% (95% CI 6–40%)].” We rounded up the pooled value to 25% in these simulations for simplicity. [Rabie, T. and Curtis, V.](https://onlinelibrary.wiley.com/doi/full/10.1111/j.1365-3156.2006.01568.x) Note: as this meta-analysis points out, the quality of studies for handwashing (at least in high-income countries) are awful.

[^london]: “We found a 73% reduction in the average daily number of contacts observed per participant. This would be sufficient to reduce R0 from a value from 2.6 before the lockdown to 0.62 (0.37 - 0.89) during the lockdown”. We rounded it down to 70% in these simulations for simplicity. [Jarvis and Zandvoort et al](https://cmmid.github.io/topics/covid19/comix-impact-of-physical-distance-measures-on-transmission-in-the-UK.html)

**この計算機をいじって非-<icon s></icon>%、手洗い、距離戦略が R を減少させるかを確かめてみよう:** (この計算機は**相対的**な効果を視覚化するので、1つを増加すると他の効果が減少したかのように見える。[^log_caveat])

[^log_caveat]: This distortion would go away if we plotted R on a logarithmic scale... but then we'd have to explain *logarithmic scales.*

<div class="sim">
		<iframe src="sim?stage=int-2a&format=calc" width="285" height="260"></iframe>
</div>

次に、2020年3月から手洗いを増加させたが、**軽い**物理的距離戦略を取って、R は減少したが 1以上であった場合 COVID-19 エピデミックはどうなるかをシミュレートしてみよう:

<div class="sim">
		<iframe src="sim?stage=int-2&format=lines" width="800" height="540"></iframe>
</div>

3点挙げられる:

1. これは総患者数を**減少**させる! **R < 1 を達成できなくても、R を減少させるだけで集団免疫以上の「オーバーシュート」を減少させ、命を救うことができる。** 多くの人が「曲線を平らにせよ」はただ患者数を散らばらせただけで総患者数は減らないと思っている。疫学入門のどのモデルを使ってもそれは不可能だ。しかし、ニュースが「80% が感染する」と報道したせいで、何をしても総患者数は変わらないと思っている。やれやれ。

2. 介入を強化することで、現在患者数は集団免疫を達成する**前**にピークする。事実このシミュレーションでは総患者数は集団免疫よりもほんのちょっとだけオーバーシュートする - これがイギリスの計画だ。その時点で R < 1 となり、全ての介入を解除しても COVID-19 は封鎖されたままとなる! ただし、1つだけ問題がある...

3. ICU は足りなくなる。しかも数ヶ月に渡って。(これらのシミュレーションでは既に ICU のキャパシティーを 3倍に上げていることを思い出してほしい)

これがインペリアル・カレッジ・ロンドンの3月16日の報告書のもう 1つの知見で、これがイギリス政府の元の計画を捨てることを説得させた。全ての**緩和策** (R を減少させるが、R > 1) は失敗する。**抑制策** (R < 1 となるように R を減少させる) のみが唯一の道なのだ。

![](pics/mitigation_vs_suppression.png)

つまり、曲線を「平ら」にするのではなく、**潰す**必要がある。

### シナリオ 2: 数ヶ月に渡るロックダウン

5ヶ月に渡ってロックダウンして曲線を**潰して**、<icon i></icon> をほぼ無にして、やっと普通の生活に戻った場合を考察する:

<div class="sim">
		<iframe src="sim?stage=int-3&format=lines" width="800" height="540"></iframe>
</div>

ダメだ。

これが、皆が言っている「第二波」というものだ。ロックダウンを解除すると再び R > 1 となってしまう。そのため、1人残った <icon i></icon> (もしくは海外から来た <icon i></icon>) がシナリオ 0: 一切何もしないと同じような急上昇を発生させてしまう。

**ロックダウンは治療ではなく、ただのリスタートだ。**

ということは、何度もロックダウンを繰り返す必要があるのだろうか?

### Scenario 3:  断続的ロックダウン

この解決策は最初にインペリアル・カレッジ・ロンドンの3月16日の報告書で提案され、後にハーバードの論文でも提案された。[^lockdown_harvard]

[^lockdown_harvard]: “Absent other interventions, a key metric for the success of social distancing is whether critical care capacities are exceeded. To avoid this, prolonged or intermittent social distancing may be necessary into 2022.” [Kissler and Tedijanto et al](https://science.sciencemag.org/content/early/2020/04/14/science.abb5793)

**シミュレートしてみよう:** (「録画されたシナリオ」を再生した後、シミュレーションが走っている間にスライダーを変化させて独自のロックダウンのスケジュールを試してほしい! シミュレーションを一時停止したり、スピードを変えることも可能だ。)

<div class="sim">
		<iframe src="sim?stage=int-4&format=lines" width="800" height="540"></iframe>
</div>

この方法は患者数を ICU のキャパシティ以下に抑えることができる! そしてワクチンができるまで 18ヶ月間ロックダウンするよりは良い方法だ。ただ私たちは... 数ヶ月シャットダウンして、数ヶ月店開きして、というのをワクチンができるまで繰り返すことになる。(ワクチンが見つからなければ、集団免疫が得られる 2022年までそれを続けることになる)

「ICU キャパシティ」と書いた線を引くのは良いが、シミュレートすることができない大切な事が多くあるこを忘れてはいけない。例えば:

**メンタルヘルス:** Loneliness is one of the biggest risk factors for depression, anxiety, and suicide. And it's as associated with an early death as smoking 15 cigarettes a day.[^loneliness]

[^loneliness]: See [Figure 6 from Holt-Lunstad & Smith 2010](https://journals.sagepub.com/doi/abs/10.1177/1745691614568352). Of course, big disclaimer that they found a *correlation*. But unless you want to try randomly assigning people to be lonely for life, observational evidence is all you're gonna get.

**Financial Health:** "What about the economy" sounds like you care more about dollars than lives, but "the economy" isn't just stocks: it's people's ability to provide food & shelter for their loved ones, to invest in their kids' futures, and enjoy arts, foods, videogames – the stuff that makes life worth living. And besides, poverty *itself* has horrible impacts on mental and physical health.

Not saying we *shouldn't* lock down again! We'll look at "circuit breaker" lockdowns later. Still, it's not ideal.

But wait... haven't Taiwan and South Korea *already* contained COVID-19? For 4 whole months, *without* long-term lockdowns?

How?

### Scenario 4: Test, Trace, Isolate

*"Sure, we \*could've\* done what Taiwan & South Korea did at the start, but it's too late now. We missed the start."*

But that's exactly it! “A lockdown isn't a cure, it's just a restart”... **and a fresh start is what we need.**

To understand how Taiwan & South Korea contained COVID-19, we need to understand the exact timeline of a typical COVID-19 infection[^timeline]:

[^timeline]: **3 days on average to infectiousness:** “Assuming an incubation period distribution of mean 5.2 days from a separate study of early COVID-19 cases, we inferred that infectiousness started from 2.3 days (95% CI, 0.8–3.0 days) before symptom onset” (translation: Assuming symptoms start at 5 days, infectiousness starts 2 days before = Infectiousness starts at 3 days) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)  
    
    **4 days on average to infecting someone else:** “The mean [serial] interval was 3.96 days (95% CI 3.53–4.39 days)” [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article)
    
    **5 days on average to feeling symptoms:** “The median incubation period was estimated to be 5.1 days (95% CI, 4.5 to 5.8 days)” [Lauer SA, Grantz KH, Bi Q, et al](https://annals.org/AIM/FULLARTICLE/2762808/INCUBATION-PERIOD-CORONAVIRUS-DISEASE-2019-COVID-19-FROM-PUBLICLY-REPORTED)

![](pics/timeline1.png)

If cases only self-isolate when they know they're sick (that is, they feel symptoms), the virus can still spread:

![](pics/timeline2.png)

And in fact, 44% of all transmissions are like this: *pre*-symptomatic! [^pre_symp]

[^pre_symp]: “We estimated that 44% (95% confidence interval, 25–69%) of secondary cases were infected during the index cases’ presymptomatic stage” [He, X., Lau, E.H.Y., Wu, P. et al](https://www.nature.com/articles/s41591-020-0869-5)

But, if we find *and quarantine* a symptomatic case's recent close contacts... we stop the spread, by staying one step ahead!

![](pics/timeline3.png)

This is called **contact tracing**. It's an old idea, was used at an unprecedented scale to contain Ebola[^ebola], and now it's core part of how Taiwan & South Korea are containing COVID-19!

[^ebola]: “Contact tracing was a critical intervention in Liberia and represented one of the largest contact tracing efforts during an epidemic in history.” [Swanson KC, Altare C, Wesseh CS, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6152989/)

(It also lets us use our limited tests more efficiently, to find pre-symptomatic <icon i></icon>s without needing to test almost everyone.)

Traditionally, contacts are found with in-person interviews, but those *alone* are too slow for COVID-19's ~48 hour window. That's why contact tracers need help, and be supported by – *NOT* replaced by – contact tracing apps.

(This idea didn't come from "techies": using an app to fight COVID-19 was first proposed by [a team of Oxford epidemiologists](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936).)

Wait, apps that trace who you've been in contact with?... Does that mean giving up privacy, giving in to Big Brother?

Heck no! **[DP-3T](https://github.com/DP-3T/documents#decentralized-privacy-preserving-proximity-tracing)**, a team of epidemiologists & cryptographers (including one of us, Marcel Salathé) is *already* making a contact tracing app – with code available to the public – that reveals **no info about your identity, location, who your contacts are, or even *how many contacts* you've had.**

Here's how it works:

![](pics/dp3t.png)

(& [here's the full comic](https://ncase.me/contact-tracing/))

Along with similar teams like TCN Protocol[^tcn] and MIT PACT[^pact], they've inspired Apple & Google to bake privacy-first contact tracing directly into Android/iOS.[^gapple] (Don't trust Google/Apple? Good! The beauty of this system is it doesn't *need* trust!) Soon, your local public health agency may ask you to download an app. If it's privacy-first with publicly-available code, please do!

[^tcn]: [Temporary Contact Numbers, a decentralized, privacy-first contact tracing protocol](https://github.com/TCNCoalition/TCN#tcn-protocol)

[^pact]: [PACT: Private Automated Contact Tracing](https://pact.mit.edu/)

[^gapple]: [Apple and Google partner on COVID-19 contact tracing technology ](https://www.apple.com/ca/newsroom/2020/04/apple-and-google-partner-on-covid-19-contact-tracing-technology/). Note they're not making the apps *themselves*, just creating the systems that will *support* those apps.

But what about folks without smartphones? Or infections through doorknobs? Or "true" asymptomatic cases? Contact tracing apps can't catch all transmissions... *and that's okay!* We don't need to catch *all* transmissions, just 60%+ to get R < 1.

(Rant about the confusion about pre-symptomatic vs "true" asymptomatic. "True" asymptomatics are rare:[^rant])

[^rant]: Lots of news reports – and honestly, many research papers – did not distinguish between "cases who showed no symptoms when we tested them" (pre-symptomatic) and "cases who showed no symptoms *ever*" (true asymptomatic). The only way you could tell the difference is by following up with cases later.
   
    Which is what [this study](https://wwwnc.cdc.gov/eid/article/26/8/20-1274_article) did. (Disclaimer: "Early release articles are not considered as final versions.") In a call center in South Korea that had a COVID-19 outbreak, "only 4 (1.9%) remained asymptomatic within 14 days of quarantine, and none of their household contacts acquired secondary infections."
    
    So that means "true asymptomatics" are rare, and catching the disease from a true asymptomatic may be even rarer!

Isolating *symptomatic* cases would reduce R by up to 40%, and quarantining their *pre/a-symptomatic* contacts would reduce R by up to 50%[^oxford]:

[^oxford]: From the same Oxford study that first recommended apps to fight COVID-19: [Luca Ferretti & Chris Wymant et al](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936/tab-figures-data) See Figure 2. Assuming R<sub>0</sub> = 2.0, they found that:    
    
    * Symptomatics contribute R = 0.8 (40%)
    * Pre-symptomatics contribute R = 0.9 (45%)
    * Asymptomatics contribute R = 0.1 (5%, though their model has uncertainty and it could be much lower)
    * Environmental stuff like doorknobs contribute R = 0.2 (10%)

    And add up the pre- & a-symptomatic contacts (45% + 5%) and you get 50% of R!

<div class="sim">
		<iframe src="sim?stage=int-4a&format=calc" width="285" height="340"></iframe>
</div>

Thus, even without 100% contact quarantining, we can get R < 1 *without a lockdown!* Much better for our mental & financial health. (As for the cost to folks who have to self-isolate/quarantine, *governments should support them* – pay for the tests, job protection, subsidized paid leave, etc. Still way cheaper than intermittent lockdown.)

We then keep R < 1 until we have a vaccine, which turns susceptible <icon s></icon>s into immune <icon r></icon>s. Herd immunity, the *right* way:

<div class="sim">
		<iframe src="sim?stage=int-4b&format=calc" width="285" height="230"></iframe>
</div>

(Note: this calculator pretends the vaccines are 100% effective. Just remember that in reality, you'd have to compensate by vaccinating *more* than "herd immunity", to *actually* get herd immunity)

Okay, enough talk. Here's a simulation of:

1. A few-month lockdown, until we can...
2. Switch to "Test, Trace, Isolate" until we can...
3. Vaccinate enough people, which means...
4. We win.

<div class="sim">
		<iframe src="sim?stage=int-5&format=lines" width="800" height="540"></iframe>
</div>

So that's it! That's how we make an emergency landing on this plane.

That's how we beat COVID-19.

...

But what if things *still* go wrong? Things have gone horribly wrong already. That's fear, and that's good! Fear gives us energy to create *backup plans*.

The pessimist invents the parachute.

###Scenario 4+: Masks For All, Summer, Circuit Breakers

What if R<sub>0</sub> is way higher than we thought, and the above interventions, even with mild distancing, *still* aren't enough to get R < 1?

Remember, even if we can't get R < 1, reducing R still reduces the "overshoot" in total cases, thus saving lives. But still, R < 1 is the ideal, so here's a few other ways to reduce R:

**Masks For All:**

*"Wait,"* you might ask, *"I thought face masks don't stop you from getting sick?"*

You're right. Masks don't stop you from getting sick[^incoming]... they stop you from getting *others* sick.

[^incoming]: “None of these surgical masks exhibited adequate filter performance and facial fit characteristics to be considered respiratory protection devices.” [Tara Oberg & Lisa M. Brosseau](https://www.sciencedirect.com/science/article/pii/S0196655307007742)

[^outgoing]: “The overall 3.4 fold reduction [70% reduction] in aerosol copy numbers we observed combined with a nearly complete elimination of large droplet spray demonstrated by Johnson et al. suggests that surgical masks worn by infected persons could have a clinically significant impact on transmission.” [Milton DK, Fabian MP, Cowling BJ, Grantham ML, McDevitt JJ](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3591312/)

[^homemade]: [Davies, A., Thompson, K., Giri, K., Kafatos, G., Walker, J., & Bennett, A](https://www.cambridge.org/core/journals/disaster-medicine-and-public-health-preparedness/article/testing-the-efficacy-of-homemade-masks-would-they-protect-in-an-influenza-pandemic/0921A05A69A9419C862FA2F35F819D55) See Table 1: a 100% cotton T-shirt has around 2/3 the filtration efficiency as a surgical mask, for the two bacterial aerosols they tested.

![](pics/masks.png)

To put a number on it: surgical masks *on the sick person* reduce cold & flu viruses in aerosols by 70%.[^outgoing] Reducing transmissions by 70% would be as large an impact as a lockdown!

However, we don't know for sure the impact of masks on COVID-19 *specifically*. In science, one should only publish a finding if you're 95% sure of it. (...should.[^replication]) Masks, as of May 1st 2020, are less than "95% sure".

[^replication]: Any actual scientist who read that last sentence is probably laugh-crying right now. See: [p-hacking](https://en.wikipedia.org/wiki/Data_dredging), [the replication crisis](https://en.wikipedia.org/wiki/Replication_crisis))

However, pandemics are like poker. **Make bets only when you're 95% sure, and you'll lose everything at stake.** As a recent article on masks in the British Medical Journal notes,[^precautionary] we *have* to make cost/benefit analyses under uncertainty. Like so:

[^precautionary]: “It is time to apply the precautionary principle” [Trisha Greenhalgh et al \[PDF\]](https://www.bmj.com/content/bmj/369/bmj.m1435.full.pdf)

Cost: If homemade cloth masks (which are ~2/3 as effective as surgical masks[^homemade]), super cheap. If surgical masks, more expensive but still pretty cheap.

Benefit: Even if it's a 50–50 chance of surgical masks reducing transmission by 0% or 70%, the average "expected value" is still 35%, same as a half-lockdown! So let's guess-timate that surgical masks reduce R by up to 35%, discounted for our uncertainty. (Again, you can challenge our assumptions by turning the sliders up/down)

<div class="sim">
		<iframe src="sim?stage=int-6a&format=calc" width="285" height="380"></iframe>
</div>

(other arguments for/against masks:[^mask_args])

[^mask_args]: **"We need to save supplies for hospitals."** *Absolutely agreed.* But that's more of an argument for increasing mask production, not rationing. In the meantime, we can make cloth masks.

   **"They're hard to wear correctly."** It's also hard to wash your hands according to the WHO Guidelines – seriously, "Step 3) right palm over left dorsum"?! – but we still recommend handwashing, because imperfect is still better than nothing.
   
   **"It'll make people more reckless with handwashing & social distancing."** Sure, and safety belts make people ignore stop signs, and flossing makes people eat rocks. But seriously, we'd argue the opposite: masks are a *constant physical reminder* to be careful – and in East Asia, masks are also a symbol of solidarity!
    
    

Masks *alone* won't get R < 1. But if handwashing & "Test, Trace, Isolate" only gets us to R = 1.10, having just 1/3 of people wear masks would tip that over to R < 1, virus contained!

**Summer:**

Okay, this isn't an "intervention" we can control, but it will help! Some news outlets report that summer won't do anything to COVID-19. They're half right: summer won't get R < 1, but it *will* reduce R.

For COVID-19, every extra 1° Celsius (2.2° Fahrenheit) makes R drop by 1.2%.[^heat] The summer-winter difference in New York City is 15°C (60°F), so summer will make R drop by 18%.

[^heat]: “One-degree Celsius increase in temperature [...] lower[s] R by 0.0225” and “The average R-value of these 100 cities is 1.83”. 0.0225 ÷ 1.83 = ~1.2%. [Wang, Jingyuan and Tang, Ke and Feng, Kai and Lv, Weifeng](https://papers.ssrn.com/sol3/Papers.cfm?abstract_id=3551767)

<div class="sim">
		<iframe src="sim?stage=int-6b&format=calc" width="285" height="220"></iframe>
</div>

Summer alone won't make R < 1, but if we have limited resources, we can scale back some interventions in the summer – so we can scale them *higher* in the winter.

**A "Circuit Breaker" Lockdown:**

And if all that *still* isn't enough to get R < 1... we can do another lockdown.

But we wouldn't have to be 2-months-closed / 1-month-open over & over! Because R is reduced, we'd only need one or two more "circuit breaker" lockdowns before a vaccine is available. (Singapore had to do this recently, "despite" having controlled COVID-19 for 4 months. That's not failure: this *is* what success takes.)

Here's a simulation a "lazy case" scenario:

1. Lockdown, then
2. A moderate amount of hygiene & "Test, Trace, Isolate", with a mild amount of "Masks For All", then...
3. One more "circuit breaker" lockdown before a vaccine's found.

<div class="sim">
		<iframe src="sim?stage=int-7&format=lines&height=620" width="800" height="620"></iframe>
</div>

Not to mention all the *other* interventions we could do, to further push R down:

* Travel restrictions/quarantines
* Temperature checks at malls & schools
* Deep-cleaning public spaces
* [Replacing hand-shaking with foot-bumping](https://twitter.com/V_actually/status/1233785527788285953)
* And all else human ingenuity shall bring

. . .

We hope these plans give you hope. 

**Even under a pessimistic scenario, it *is* possible to beat COVID-19, while protecting our mental and financial health.** Use the lockdown as a "reset button", keep R < 1 with case isolation + privacy-protecting contract tracing + at *least* cloth masks for all... and life can get back to a normal-ish!

Sure, you may have dried-out hands. But you'll get to invite a date out to a comics bookstore! You'll get to go out with friends to watch the latest Hollywood cash-grab. You'll get to people-watch at a library, taking joy in people going about the simple business of *being alive.*

Even under the worst-case scenario... life perseveres.

So now, let's plan for some *worse* worst-case scenarios. Water landing, get your life jacket, and please follow the lights to the emergency exits:

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>The Next Few Years</div>
    </div>
</div>

You get COVID-19, and recover. Or you get the COVID-19 vaccine. Either way, you're now immune...

...*for how long?*

* COVID-19 is most closely related to SARS, which gave its survivors 2 years of immunity.[^SARS immunity]
* The coronaviruses that cause "the" common cold give you 8 months of immunity.[^cold immunity]
* There's reports of folks recovering from COVID-19, then testing positive again, but it's unclear if these are false positives.[^unclear]
* One *not-yet-peer-reviewed* study on monkeys showed immunity to the COVID-19 coronavirus for at least 28 days.[^monkeys]

But for COVID-19 *in humans*, as of May 1st 2020, "how long" is the big unknown.

[^SARS immunity]: “SARS-specific antibodies were maintained for an average of 2 years [...] Thus, SARS patients might be susceptible to reinfection ≥3 years after initial exposure.” [Wu LP, Wang NC, Chang YH, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2851497/) "Sadly" we'll never know how long SARS immunity would have really lasted, since we eradicated it so quickly.

[^cold immunity]: “We found no significant difference between the probability of testing positive at least once and the probability of a recurrence for the beta-coronaviruses HKU1 and OC43 at 34 weeks after enrollment/first infection.” [Marta Galanti & Jeffrey Shaman (PDF)](http://www.columbia.edu/~jls106/galanti_shaman_ms_supp.pdf)

[^unclear]: “Once a person fights off a virus, viral particles tend to linger for some time. These cannot cause infections, but they can trigger a positive test.” [from STAT News by Andrew Joseph](https://www.statnews.com/2020/04/20/everything-we-know-about-coronavirus-immunity-and-antibodies-and-plenty-we-still-dont/)

[^monkeys]: From [Bao et al.](https://www.biorxiv.org/content/10.1101/2020.03.13.990226v1.abstract) *Disclaimer: This article is a preprint and has not been certified by peer review (yet).* Also, to emphasize: they only tested re-infection 28 days later. 

For these simulations, let's say it's 1 year.
**Here's a simulation starting with 100% <icon r></icon>**, exponentially decaying into susceptible, no-immunity <icon s></icon>s after 1 year, on *average*, with variation:

<div class="sim">
		<iframe src="sim?stage=yrs-1&format=lines&height=600" width="800" height="600"></iframe>
</div>

Return of the exponential decay!

This is the **SEIRS Model**. The final "S" stands for <icon s></icon> Susceptible, again.

![](pics/seirs.png)

Now, let's simulate a COVID-19 outbreak, over 10 years, with no interventions... *if immunity only lasts a year:*

<div class="sim">
		<iframe src="sim?stage=yrs-2&format=lines&height=600" width="800" height="600"></iframe>
</div>

In previous simulations, we only had *one* ICU-overwhelming spike. Now, we have several, *and* <icon i></icon> cases come to a rest *permanently at* ICU capacity. (Which, remember, we *tripled* for these simulations)

R = 1, it's **endemic.**

Thankfully, because summer reduces R, it'll make the situation better:

<div class="sim">
		<iframe src="sim?stage=yrs-3&format=lines&height=640" width="800" height="640"></iframe>
</div>

Oh.

Counterintuitively, summer makes the spikes worse *and* regular! This is because summer reduces new <icon i></icon>s, but that in turn reduces new immune <icon r></icon>s. Which means immunity plummets in the summer, *creating* large regular spikes in the winter.

Thankfully, the solution to this is pretty straightforward – just vaccinate people every fall/winter, like we do with flu shots:

**(After playing the recording, try simulating your own vaccination campaigns! Remember you can pause/continue the sim at any time)**

<div class="sim">
		<iframe src="sim?stage=yrs-4&format=lines" width="800" height="540"></iframe>
</div>

But here's the scarier question:

What if there's no vaccine for *years*? Or *ever?*

**To be clear: this is unlikely.** Most epidemiologists expect a vaccine in 1 to 2 years. Sure, there's never been a vaccine for any of the other coronaviruses before, but that's because SARS was eradicated quickly, and "the" common cold wasn't worth the investment. 

Still, infectious disease researchers have expressed worries: What if we can't make enough?[^vax_enough] What if we rush it, and it's not safe?[^vax_safe]

[^vax_enough]: “If a coronavirus vaccine arrives, can the world make enough?” [by Roxanne Khamsi, on Nature](https://www.nature.com/articles/d41586-020-01063-8)

[^vax_safe]: “Don’t rush to deploy COVID-19 vaccines and drugs without sufficient safety guarantees” [by Shibo Jiang, on Nature](https://www.nature.com/articles/d41586-020-00751-9)

Even in the nightmare "no-vaccine" scenario, we still have 3 ways out. From most to least terrible:

1) Do intermittent or loose R < 1 interventions, to reach "natural herd immunity". (Warning: this will result in many deaths & damaged lungs. *And* won't work if immunity doesn't last.)

2) Do the R < 1 interventions forever. Contact tracing & wearing masks just becomes a new norm in the post-COVID-19 world, like how STI tests & wearing condoms became a new norm in the post-HIV world.

3) Do the R < 1 interventions until we develop treatments that make COVID-19 way, way less likely to need critical care. (Which we should be doing *anyway!*) Reducing ICU use by 10x is the same as increasing our ICU capacity by 10x:

**Here's a simulation of *no* lasting immunity, *no* vaccine, and not even any interventions – just slowly increasing capacity to survive the long-term spikes:**

<div class="sim">
		<iframe src="sim?stage=yrs-5&format=lines" width="800" height="540"></iframe>
</div>

Even under the *worst* worst-case scenario... life perseveres.

. . .

Maybe you'd like to challenge our assumptions, and try different R<sub>0</sub>'s or numbers. Or try simulating your *own* combination of intervention plans!

**Here's an (optional) Sandbox Mode, with *everything* available. (scroll to see all controls) Simulate & play around to your heart's content:**

<div class="sim">
		<iframe src="sim?stage=SB&format=sb" width="800" height="540"></iframe>
</div>

This basic "epidemic flight simulator" has taught us so much. It's let us answer questions about the past few months, next few months, and next few years.

So finally, let's return to...

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>The Now</div>
    </div>
</div>

Plane's sunk. We've scrambled onto the life rafts. It's time to find dry land.[^dry_land]

[^dry_land]: Dry land metaphor [from Marc Lipsitch & Yonatan Grad, on STAT News](https://www.statnews.com/2020/04/01/navigating-covid-19-pandemic/)

Teams of epidemiologists and policymakers ([left](https://www.americanprogress.org/issues/healthcare/news/2020/04/03/482613/national-state-plan-end-coronavirus-crisis/), [right](https://www.aei.org/research-products/report/national-coronavirus-response-a-road-map-to-reopening/ ), and [multi-partisan](https://ethics.harvard.edu/covid-roadmap)) have come to a consensus on how to beat COVID-19, while protecting our lives *and* liberties.

Here's the rough idea, with some (less-consensus) backup plans:

![](pics/plan.png)

So what does this mean for YOU, right now?

**For everyone:** Respect the lockdown so we can get out of Phase I asap. Keep washing those hands. Make your own masks. Download a *privacy-protecting* contact tracing app when those are available next month. Stay healthy, physically & mentally! And write your local policymaker to get off their butt and...

**For policymakers:** Make laws to support folks who have to self-isolate/quarantine. Hire more manual contact tracers, *supported* by privacy-protecting contact tracing apps. Direct more funds into the stuff we should be building, like...

**For builders:** Build tests. Build ventilators. Build personal protective equipment for hospitals. Build tests. Build masks. Build apps. Build antivirals, prophylactics, and other treatments that aren't vaccines. Build vaccines. Build tests. Build tests. Build tests. Build hope. 

Don't downplay fear to build up hope. Our fear should *team up* with our hope, like the inventors of airplanes & parachutes. Preparing for horrible futures is how we *create* a hopeful future.

The only thing to fear is the idea that the only thing to fear is fear itself.