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

**疫学者は感染症シミュレーターを使って人類を墜落させない方法を学ぶ。**

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

このことは感染症の成長にどう影響があるだろうか? 確かめてみよう:

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

「感染症フライト・シミュレーター」を使って以下を考えてみよう: **メンタルヘルスと金銭的な健全性の両方を保護する形**で R < 1 を達成するにはどうすればいいだろうか?

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

次に、2020年3月から手洗いを増加させたが、**軽い**物理的距離戦略を取って、R は減少したが 1以上であった場合 COVID-19 感染症はどうなるかをシミュレートしてみよう:

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

**ロックダウンは特効薬ではなく、ただのリスタートだ。**

ということは、何度もロックダウンを繰り返す必要があるのだろうか?

### シナリオ 3:  断続的ロックダウン

この解決策は最初にインペリアル・カレッジ・ロンドンの3月16日の報告書で提案され、後にハーバードの論文でも提案された。[^lockdown_harvard]

[^lockdown_harvard]: “Absent other interventions, a key metric for the success of social distancing is whether critical care capacities are exceeded. To avoid this, prolonged or intermittent social distancing may be necessary into 2022.” [Kissler and Tedijanto et al](https://science.sciencemag.org/content/early/2020/04/14/science.abb5793)

**シミュレートしてみよう:** (「録画されたシナリオ」を再生した後、シミュレーションが走っている間にスライダーを変化させて独自のロックダウンのスケジュールを試してほしい! シミュレーションを一時停止したり、スピードを変えることも可能だ。)

<div class="sim">
		<iframe src="sim?stage=int-4&format=lines" width="800" height="540"></iframe>
</div>

この方法は患者数を ICU のキャパシティ以下に抑えることができる! そしてワクチンができるまで 18ヶ月間ロックダウンするよりは良い方法だ。ただ私たちは... 数ヶ月シャットダウンして、数ヶ月店開きして、というのをワクチンができるまで繰り返すことになる。(ワクチンが見つからなければ、集団免疫が得られる 2022年までそれを続けることになる)

「ICU キャパシティ」と書いた線を引くのは良いが、シミュレートすることができない大切な事が多くあるこを忘れてはいけない。例えば:

**メンタルヘルス:** 孤独はうつ病、不安症、自殺の大きなリスクファクターの 1つだ。1日に 15本のタバコを吸うのと同じぐらい早死にすると関連付けられている。[^loneliness]

[^loneliness]: See [Figure 6 from Holt-Lunstad & Smith 2010](https://journals.sagepub.com/doi/abs/10.1177/1745691614568352). Of course, big disclaimer that they found a *correlation*. But unless you want to try randomly assigning people to be lonely for life, observational evidence is all you're gonna get.

**金銭的な健全性:** 「経済のために」と言うと、人の命よりも金を大切にするのか思われがちだが、「経済」はただの株だけでは無い。人々が衣食住を家族に提供したり、子供将来に投資したり、芸術や料理やテレビゲームを楽しんで、人生を生きていて良かったことにするものも経済なのだ。それ以外でも、貧困そのものもメンタルやフィジカルな面で健康に悪い。

ロックダウンをもう二度とするべきではないと言っているわけではない! 「ブレーカー」ロックダウンも後で考察する。いずれにせよ、ロックダウンは理想的では無い。

しかし待ってほしい。台湾や韓国は既に COVID-19 を封じ込めたのではないだろうか? 丸々4ヶ月間ロックダウン無しで?

どうやったのだろう?

### シナリオ 4: 検査、追跡、隔離

**「アウトブレイク当初ならば台湾や韓国みたいなことができたけど、もう遅い。我々は当初の機を逃したんだよ。」**

しかし、思い出してほしい! 「ロックダウンは特効薬ではなく、ただのリスタートだ。」... そして**仕切り直し**は正に私たちに必要な事だ。

台湾や韓国がどう COVID-19 を封じ込めたのかを理解するには、まずは典型的な COVID-19 感染の正確な経過を知る必要がある[^timeline]:

[^timeline]: **3 days on average to infectiousness:** “Assuming an incubation period distribution of mean 5.2 days from a separate study of early COVID-19 cases, we inferred that infectiousness started from 2.3 days (95% CI, 0.8–3.0 days) before symptom onset” (translation: Assuming symptoms start at 5 days, infectiousness starts 2 days before = Infectiousness starts at 3 days) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)  
    
    **4 days on average to infecting someone else:** “The mean [serial] interval was 3.96 days (95% CI 3.53–4.39 days)” [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article)
    
    **5 days on average to feeling symptoms:** “The median incubation period was estimated to be 5.1 days (95% CI, 4.5 to 5.8 days)” [Lauer SA, Grantz KH, Bi Q, et al](https://annals.org/AIM/FULLARTICLE/2762808/INCUBATION-PERIOD-CORONAVIRUS-DISEASE-2019-COVID-19-FROM-PUBLICLY-REPORTED)

![](pics/timeline1.png)

もし患者が自分が病気であると分かった時 (つまり自覚症状がある場合) にのみ自己隔離した場合は、ウイルスは拡散し続ける:

![](pics/timeline2.png)

事実全ての伝染の 44% は発症前だ! [^pre_symp]

[^pre_symp]: “We estimated that 44% (95% confidence interval, 25–69%) of secondary cases were infected during the index cases’ presymptomatic stage” [He, X., Lau, E.H.Y., Wu, P. et al](https://www.nature.com/articles/s41591-020-0869-5)

しかし、発症している患者の近日中の接触者を探して、**隔離**すれば、一歩先を行くことで拡散は防止できる!

![](pics/timeline3.png)

これは、**コンタクト・トレーシング**と呼ばれる。これは、古いアイディアで、エボラの封じ込めのために先例のない規模で行われ、台湾や韓国の COVID-19 封じ込め戦略の中核を成している!

[^ebola]: “Contact tracing was a critical intervention in Liberia and represented one of the largest contact tracing efforts during an epidemic in history.” [Swanson KC, Altare C, Wesseh CS, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6152989/)

(ほぼ全員を検査する代わりに、限られた検査を使ってより効率的に発症前の<icon i></icon> の人を探すことを可能とする。)

従来では接触者は対人の面接を行って発見してきたが、**それだけ**だと COVID-19 の ~48時間の窓口には遅すぎる。そのため接触追跡をする人は助けが必要で、コンタクト・トレーシング・アプリが支援を行う。飽くまで支援であって、接触追跡を置き換える訳ではないことに注意してほしい。

(このアイディアは「技術屋」から出てきたわけじゃない: アプリを使って COVID-19 と戦うというのは最初に[オックスフォード大学の疫学者チーム](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936)から提案された。)

自分が誰と接触したかを追跡するアプリだって? ということは、ビッグ・ブラザーにプライバシーを明け渡すってことなのだろうか?

冗談じゃない! **[DP-3T](https://github.com/DP-3T/documents#decentralized-privacy-preserving-proximity-tracing)** という疫学者と暗号学者から成るチーム (著者の 1人 Marcel Salathé を含む) は既にコードを公開した形でコンタクト・トレーシング・アプリを作っていて、それは**一切あなたのアイデンティティー、位置情報、接触情報などを一切明かさない**ようになっている。

以下のような仕組みだ:

![](pics/dp3t.png)

([このマンガの完全版](https://ncase.me/contact-tracing/)参照)

TCN Protocol[^tcn] や MIT PACT[^pact] といった同様のチームと共に彼らは Apple と Google がプライバシー・ファーストなコンタクト・トレーシングを Android と iOS に組み込むインスピレーションとなった。[^gapple] (Google や Apple を信頼できないって? このシステムの良さは、信頼を必要としない事だ。) いずれ公衆衛生機関がアプリをダウンロードするように言ってくるかもしれない。もしも、これがプライバシー・ファーストで公開されたコードならば是非ダウンロードしてほしい!

[^tcn]: [Temporary Contact Numbers, a decentralized, privacy-first contact tracing protocol](https://github.com/TCNCoalition/TCN#tcn-protocol)

[^pact]: [PACT: Private Automated Contact Tracing](https://pact.mit.edu/)

[^gapple]: [Apple and Google partner on COVID-19 contact tracing technology ](https://www.apple.com/ca/newsroom/2020/04/apple-and-google-partner-on-covid-19-contact-tracing-technology/). Note they're not making the apps *themselves*, just creating the systems that will *support* those apps.

スマートフォンを持っていない人はどうするのだろうか? もしくはドアノブからの感染? もしくは「真の」無症状の患者からの感染? コンタクト・トレーシング・アプリは全ての伝染をキャッチすることはできない... **それでも大丈夫!** 私たちは**全て**の伝染を防ぐ必要は無く、60%+ さえ防げれば R < 1 を得られるからだ。

(発症前と「真の」無症状の混乱に関する愚痴。「真の」無症状はまれだ:[^rant])

[^rant]: Lots of news reports – and honestly, many research papers – did not distinguish between "cases who showed no symptoms when we tested them" (pre-symptomatic) and "cases who showed no symptoms *ever*" (true asymptomatic). The only way you could tell the difference is by following up with cases later.
   
    Which is what [this study](https://wwwnc.cdc.gov/eid/article/26/8/20-1274_article) did. (Disclaimer: "Early release articles are not considered as final versions.") In a call center in South Korea that had a COVID-19 outbreak, "only 4 (1.9%) remained asymptomatic within 14 days of quarantine, and none of their household contacts acquired secondary infections."
    
    So that means "true asymptomatics" are rare, and catching the disease from a true asymptomatic may be even rarer!

**発症している**患者を隔離することで R を最大 40% 減少させることができ、そして彼らの接触者を発症前に隔離することで R を最大 50% 減少させることができる[^oxford]:

[^oxford]: From the same Oxford study that first recommended apps to fight COVID-19: [Luca Ferretti & Chris Wymant et al](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936/tab-figures-data) See Figure 2. Assuming R<sub>0</sub> = 2.0, they found that:    
    
    * Symptomatics contribute R = 0.8 (40%)
    * Pre-symptomatics contribute R = 0.9 (45%)
    * Asymptomatics contribute R = 0.1 (5%, though their model has uncertainty and it could be much lower)
    * Environmental stuff like doorknobs contribute R = 0.2 (10%)

    And add up the pre- & a-symptomatic contacts (45% + 5%) and you get 50% of R!

<div class="sim">
		<iframe src="sim?stage=int-4a&format=calc" width="285" height="340"></iframe>
</div>

そのため、接触者隔離を 100% 行わなくても、**ロックダウン無しで**　R < 1 を得ることができる! メンタル的にも金銭的にも健康的だ。(自己隔離/検疫を行わなくてはいけない人たちに対しては、検査の支払い、職業の保護、有給の助成など**政府が支援をするべきだ**。断続的ロックダウンに比べると安いものだ。)

ワクチンを得られるまで R < 1 を保持できれば、ワクチンが感受性のある人 <icon s></icon> を免疫のある <icon r></icon> へと変える。これが集団免疫の**正しい**方法だ:

<div class="sim">
		<iframe src="sim?stage=int-4b&format=calc" width="285" height="230"></iframe>
</div>

(注意: この計算機はワクチンが 100%有効であると仮定する。現実には、「集団免疫」以上にワクチンを打って補正することで実際の集団免疫を得ることができると覚えておいてほしい。)

話はもういい。以下は

1. 数ヶ月のロックダウンそして...
2. できるときに「検査、追跡、隔離」に切り替え...
3. できるときに十分な人にワクチンを接種して...
4. 勝利

するシミュレーションだ。

<div class="sim">
		<iframe src="sim?stage=int-5&format=lines" width="800" height="540"></iframe>
</div>

これで終わりだ! この飛行機はこうやって緊急着陸することができる。

これが COVID-19 に打ち勝つ方法だ。

...

しかし、それでも物事がうまくいかなかったらどうだろう? 物事は既にうまくいっていない。これは恐怖で、それは良いことだ。恐怖は、バックアッププランを立てるエネルギーを与えてくれる。

悲観論者はパラシュートを発明する。

### シナリオ 4+: 一般人のマスク着用、夏、ブレーカー

もしも R<sub>0</sub> が私たちが思っていたよりもかなり高く、上記の介入と軽度の距離戦略をもってしても R < 1 を得るのに十分じゃなかった場合はどうすればいいだろうか?

もし R < 1 を得られなかったとしても、R を減少させることで総患者数の「オーバーシュート」を軽減し、命を救うことを思い出してほしい。しかし、R < 1 が理想的なので、以下に R を減少させる他の方法を考えてみる。

**一般人のマスク着用:**

「ちょっと待った。マスクは病気にかかる予防にならないんじゃないのか?」と思ったかもしれない。

あなたは正しい。マスクはあなたが病気になる予防にはならない[^incoming]... しかしマスクはあなたが他人を病気にするのを予防してくれる。

[^incoming]: “None of these surgical masks exhibited adequate filter performance and facial fit characteristics to be considered respiratory protection devices.” [Tara Oberg & Lisa M. Brosseau](https://www.sciencedirect.com/science/article/pii/S0196655307007742)

[^outgoing]: “The overall 3.4 fold reduction [70% reduction] in aerosol copy numbers we observed combined with a nearly complete elimination of large droplet spray demonstrated by Johnson et al. suggests that surgical masks worn by infected persons could have a clinically significant impact on transmission.” [Milton DK, Fabian MP, Cowling BJ, Grantham ML, McDevitt JJ](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3591312/)

[^homemade]: [Davies, A., Thompson, K., Giri, K., Kafatos, G., Walker, J., & Bennett, A](https://www.cambridge.org/core/journals/disaster-medicine-and-public-health-preparedness/article/testing-the-efficacy-of-homemade-masks-would-they-protect-in-an-influenza-pandemic/0921A05A69A9419C862FA2F35F819D55) See Table 1: a 100% cotton T-shirt has around 2/3 the filtration efficiency as a surgical mask, for the two bacterial aerosols they tested.

![](pics/masks.png)

これに数字を付けると、**病気になった人**にサージカルマスクを付けると風邪やインフルエンザの飛沫を 70% 軽減できる。[^outgoing] 伝染の 70% を軽減できれば、それはロックダウンと同じ効果がある!

しかし、マスクが COVID-19 に対しても**確実**に有効であるかは分かっていない。科学においては、知見が 95% 確実である場合のみ論文として掲載されるべきだ (...べきだ[^replication])。2020年5月1日現在においてマスクは「95% 確実」を得ていない。

[^replication]: Any actual scientist who read that last sentence is probably laugh-crying right now. See: [p-hacking](https://en.wikipedia.org/wiki/Data_dredging), [the replication crisis](https://en.wikipedia.org/wiki/Replication_crisis))

しかし、パンデミックはポーカーのようなものだ。**95% 確実な手だけに賭けていると、賭け金を全て失うことになる**。British Medical Journal誌に最近掲載された論文[^precautionary]でも言われていたが、私たちは不確実さの中でもコスト利益分析を行う**必要**がある:

[^precautionary]: “It is time to apply the precautionary principle” [Trisha Greenhalgh et al \[PDF\]](https://www.bmj.com/content/bmj/369/bmj.m1435.full.pdf)

コスト: 手作りの布マスク (サージカルマスクに比較して ~2/3 の効果がある[^homemade]) は非常に安価だ。サージカルマスクも少し高めだが、比較的安価である。

利益: 手術用マスクが 50-50 の確率で伝染を 0% もしくは 70% 軽減させるとしても、平均した「期待値」は 35% で、これはロックダウン半分となる! 大雑把に計算するとサージカルマスクが R を最高で 35% 軽減できるとすると不確定要素を勘案したことになる。(再度言うが、スライダーを上下に動かして私たちの前提条件に物申すことができる)

<div class="sim">
		<iframe src="sim?stage=int-6a&format=calc" width="285" height="380"></iframe>
</div>

(マスクに関するその他の賛成/反対意見:[^mask_args])

[^mask_args]: **"We need to save supplies for hospitals."** *Absolutely agreed.* But that's more of an argument for increasing mask production, not rationing. In the meantime, we can make cloth masks.

   **"They're hard to wear correctly."** It's also hard to wash your hands according to the WHO Guidelines – seriously, "Step 3) right palm over left dorsum"?! – but we still recommend handwashing, because imperfect is still better than nothing.
   
   **"It'll make people more reckless with handwashing & social distancing."** Sure, and safety belts make people ignore stop signs, and flossing makes people eat rocks. But seriously, we'd argue the opposite: masks are a *constant physical reminder* to be careful – and in East Asia, masks are also a symbol of solidarity!
    
    
マスク**単体**では R < 1 を得ることができない。しかし、手洗い &「検査、追跡、隔離」のコンボでもやっと R = 1.10 しか得られない場合は、人口の 1/3 がマスクを着用するだけでも R < 1 側に倒すことができ、ウイルスを封じ込めに成功する!

**夏:**

これは、私たちが制御可能な「介入」では無いが、それでも役に立つ! 夏になっても COVID-19 は変わらないと言っている報道機関もある。彼らは半分正しいと言える: 夏だけでは R < 1 を得ることができないが、R を軽減する**効果がある**。

COVID-19 は気温が摂氏1° (華氏2.2°) 上昇するごとに、R が 1.2% 落ちると言われている。[^heat] ニューヨーク市の夏冬の気温差は 15°C (60°F) であるため、夏には R が 18% 落ちる計算となる。

[^heat]: “One-degree Celsius increase in temperature [...] lower[s] R by 0.0225” and “The average R-value of these 100 cities is 1.83”. 0.0225 ÷ 1.83 = ~1.2%. [Wang, Jingyuan and Tang, Ke and Feng, Kai and Lv, Weifeng](https://papers.ssrn.com/sol3/Papers.cfm?abstract_id=3551767)

<div class="sim">
		<iframe src="sim?stage=int-6b&format=calc" width="285" height="220"></iframe>
</div>

夏単体では R < 1 を得ることができないが、資源が限られている場合は、夏の間は介入手段を縮小させ、冬には**拡大**させるという戦略が取れる。

**「ブレーカー」ロックダウン:**

これらを全部やって**それでも** R < 1 に到達できなければ、ロックダウンを再び行うことは可能だ。

しかし、2ヶ月閉店/1ヶ月開店を延々と繰り返す必要は無い! R が十分に軽減されていれば、ワクチンが実用になるまであと 1回か 2回の「ブレーカー」的ロックダウンを行うだけでいいはずだ。(例えば、COVID-19 を 4ヶ月封じ込めたにも関わらず、最近シンガポールがこれを行う必要があった。これは失敗ではない。**正に**このようにして成功を得ることができる。)

以下が「遅延評価」シナリオのシミュレーションだ:

1. ロックダウン、次に
2. 適度な手指衛生、「検査、追跡、隔離」そして軽度の「一般人のマスク着用」...
3. そして、ワクチンが見つかる前にもう一度の「ブレーカー」ロックダウン。

<div class="sim">
		<iframe src="sim?stage=int-7&format=lines&height=620" width="800" height="620"></iframe>
</div>

R を更に抑え込むためには他にも介入手段はまだある:

* 渡航制限/検疫
* ショッピングモールや学校での体温検査
* 公共の場の消毒
* [握手の代替](https://twitter.com/V_actually/status/1233785527788285953)
* そして人類の叡智がもたらすその他の手段

. . .

これらの計画が希望をもたらすことを私たちは切に願っている。

**悲観論的シナリオにおいても、メンタルヘルスと金銭的な健全性の両方を保護する形で COVID-19 をやっつけることは可能だ**。ロックダウンは「リセット・ボタン」として用いて、患者の隔離 + プライバシーを保護したコンタクト・トレーシング + 一般人の**せめて**布マスクの着用...を組み合わせて R < 1 に保てれば、普段らしい生活に戻ることができるからだ!

手はカサカサに乾いてしまうかもしれない。しかし、マンガ本屋にデートに行くことができるようになるかもしれない! ハリウッドの最新の映画を友達と観に行くこともできる。図書館で人の観察を行ったり、人々が**生きている**ということに喜びを感じることができる。

たとえワースト・ケースのシナリオの元でも人生は頑張って続いていく必要がある。

そのため、より悪いワースト・ケースのシナリオへの対処を考察しよう。救命胴衣を着用して、照明に従って緊急出口から避難する計画だ:

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>The Next Few Years</div>
    </div>
</div>

COVID-19 に感染して、回復する。もしくは COVID-19 ワクチンを接種する。いずれにせよ、免疫を得た...

... それは**いつまで**持つのだろうか?

* COVID-19 は SARS に最も近く、SARS の生存者は 2年の免疫を獲得した。[^SARS immunity]
* 普通の風邪をもたらすコロナウイルス群からは 8ヶ月の免疫を得ることができる。[^cold immunity]
* COVID-19 から回復した後、検査で再び陽性が出た報告があるが、これが擬似陽性であるかは不確定である。[^unclear]
* **未査読**の論文1本によると、サルでは COVID-19 に対して最低でも 28日間は免疫を持つことが報告されている。[^monkeys]

2020年5月1日現在のところ、**ヒト**が COVID-19 に対して「どれだけ長く」免疫を持つのかは大きな未知要素となっている。

[^SARS immunity]: “SARS-specific antibodies were maintained for an average of 2 years [...] Thus, SARS patients might be susceptible to reinfection ≥3 years after initial exposure.” [Wu LP, Wang NC, Chang YH, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2851497/) "Sadly" we'll never know how long SARS immunity would have really lasted, since we eradicated it so quickly.

[^cold immunity]: “We found no significant difference between the probability of testing positive at least once and the probability of a recurrence for the beta-coronaviruses HKU1 and OC43 at 34 weeks after enrollment/first infection.” [Marta Galanti & Jeffrey Shaman (PDF)](http://www.columbia.edu/~jls106/galanti_shaman_ms_supp.pdf)

[^unclear]: “Once a person fights off a virus, viral particles tend to linger for some time. These cannot cause infections, but they can trigger a positive test.” [from STAT News by Andrew Joseph](https://www.statnews.com/2020/04/20/everything-we-know-about-coronavirus-immunity-and-antibodies-and-plenty-we-still-dont/)

[^monkeys]: From [Bao et al.](https://www.biorxiv.org/content/10.1101/2020.03.13.990226v1.abstract) *Disclaimer: This article is a preprint and has not been certified by peer review (yet).* Also, to emphasize: they only tested re-infection 28 days later. 

以下のシミュレーションでは、1年だと仮定しよう。
**<icon r></icon> が 100% から初め**、**平均して** 1年後に指数関数的に免疫を持たない感受性のある人 <icon s></icon> に減衰する場合のシミュレーションだ:

<div class="sim">
		<iframe src="sim?stage=yrs-1&format=lines&height=600" width="800" height="600"></iframe>
</div>

前にも見た指数関数的減衰だ!

これが **SEIRS モデル**だ。最後の「S」は <icon s></icon> 感受性 (Susceptible) に戻る。

![](pics/seirs.png)

次に、**免疫が 1年しか持続しない条件で**一切介入しない場合の今後10年の COVID-19 アウトブレイクをシミュレートしてみよう:

<div class="sim">
		<iframe src="sim?stage=yrs-2&format=lines&height=600" width="800" height="600"></iframe>
</div>

以前のシミュレーションでは ICU を圧倒する爆発的増加が **1回**のみあった。今回は、それが数回あり、なおかつ <icon i></icon> の患者数は**永遠**に ICU の収容能力満員の状態に収束した。(このシミュレーションでは**3倍化**してあるのを思い出してほしい)

R = 1 になり、これは**エンデミック** (endemic, 「地方病」、「風土病」) と呼ばれる。

幸い夏に R が軽減するので、状況は改善するだろう:

<div class="sim">
		<iframe src="sim?stage=yrs-3&format=lines&height=640" width="800" height="640"></iframe>
</div>

ダメだ。

直感に反して、夏は爆発的増加を悪化なおかつ定期的にさせる! 夏は新規の患者 <icon i></icon> を減少させるが、反面新規の免疫を持つ人 <icon r></icon> も減少させるためだ。そのため、夏になると免疫が急降下して、冬に定期的な爆発的増加が発生する条件を**作っている**ことになる。

幸い、これに対する対策は複雑で無い。インフルエンザ同様に、毎年秋/冬にワクチン接種を行えばいい:

**(録画済みのシミュレーションを再生した後、独自のワクチン接種キャンペーンを行ってみよう! 一時停止/続行をいつでも行えることを思い出してほしい)**

<div class="sim">
		<iframe src="sim?stage=yrs-4&format=lines" width="800" height="540"></iframe>
</div>

もっと怖い質問がある:

**何年間も**ワクチンが無い場合はどうすればいいだろう? もしくは、**永遠**にできない場合は?

**最初に断っておくと、この状況はまず無いと思う**。疫学者の多くは 1 から 2年の間にワクチンが開発されることを期待している。他のコロナウイルスに対するワクチンがこれまで無かったのは確かだが、SARS は早々と根絶され、普通の風邪は投資の割にあってこなかったという理由が大きい。

感染症の研究者は既に警笛を鳴らしている: 十分な量を生産できなければどうする?[^vax_enough] 急かして作って安全じゃなかった場合はどうなる?[^vax_safe]

[^vax_enough]: “If a coronavirus vaccine arrives, can the world make enough?” [by Roxanne Khamsi, on Nature](https://www.nature.com/articles/d41586-020-01063-8)

[^vax_safe]: “Don’t rush to deploy COVID-19 vaccines and drugs without sufficient safety guarantees” [by Shibo Jiang, on Nature](https://www.nature.com/articles/d41586-020-00751-9)

悪夢のような「ワクチン無し」シナリオでも、3つの解法がある。最も酷いものから最も酷くない順に見ていこう:

1) 断続的もしくは緩い R < 1 介入を行い「自然な集団免疫」を得る。(警告: これは多くの死亡者と肺への後遺症につながり、免疫性が持続しない場合はうまくいかない。)

2) R < 1 介入を永遠に行う。ポストHIV の世界では性感染症の検査を行いコンドームを使用することが新しい常識となったように、コンタクト・トレーシング & マスクの着用はポストCOVID-19世界の新しい常識となる。

3) COVID-19 が救命救急を必要とする確率が今よりも非常に小さくなるような治療法を開発するまで R < 1 の介入を行う。(これは**いずれにせよ**私たちが行うべきことだ!) ICU の使用を 10倍軽減できれば、ICU の収容キャパシティーを 10倍上げるのと同様だからだ。

**以下が、永続する免疫無し、ワクチンも無し、長期的な爆発的増加を乗り切るだけの ICU の収容キャパシティーだけを徐々に増加させる以外は介入を一切行わないシミュレーションだ:**

<div class="sim">
		<iframe src="sim?stage=yrs-5&format=lines" width="800" height="540"></iframe>
</div>

最悪のワーストケースシナリオの元でも、人生は頑張って続いていく。

. . .


私たちの前提条件に異議があって、異なる R<sub>0</sub> や他の数値を試してみたいと思ったかもしれない。もしくは、独自の介入手段の組み合わせをシミュレートしたいかもしれない!

**以下は (自由な) サンドボックス・モードで全てがいじれるようになっている。(全てのコントロールを見るにはスクロールする必要がある) 気が済むまでシミュレートしていじりたおして欲しい**:

<div class="sim">
		<iframe src="sim?stage=SB&format=sb" width="800" height="540"></iframe>
</div>

この初歩的な「感染症フライト・シミュレーター」は私たちに多くのことを教えてくれた。これは、過去数ヶ月のこと、これから数カ月後のこと、そして数年後のこと。

最後に、今のことに戻ろう。

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>今のこと</div>
    </div>
</div>

私たちは救命ボートに乗り込み、陸地を探すときが来た。[^dry_land]

[^dry_land]: Dry land metaphor [from Marc Lipsitch & Yonatan Grad, on STAT News](https://www.statnews.com/2020/04/01/navigating-covid-19-pandemic/)

疫学者と政策立案者の様々な団体 ([左寄り](https://www.americanprogress.org/issues/healthcare/news/2020/04/03/482613/national-state-plan-end-coronavirus-crisis/)、[右寄り](https://www.aei.org/research-products/report/national-coronavirus-response-a-road-map-to-reopening/ )、 [超党派](https://ethics.harvard.edu/covid-roadmap)) が私たちの生活と自由を保護した形で COVID-19 打倒する方法について一致賛成している。

以下が大まかなアイディアと (全会一致ではない) バックアップ・プランだ:

![](pics/plan.png)

これはあなたにとって何を意味するのだろうか?

**皆さんへ:** フェーズ1からなるべく早く抜け出せるように、政府機関のロックダウンに従うこと。手を洗い続けること。自分のマスクを作ってみること。来月以降**プライバシーを保護する**コンタクト・トレーシングアプリが公開されればダウンロードすること。身体的にも精神的にも健康であること! 自分を代表する政策立案者に連絡して重い腰を上げさせること。

**政策立案者の方々:** 自己隔離/検疫を行わなくてはいけない人を支援する法案を通すこと。プライバシーを保護したコンタクト・トレーシング・アプリの**支援**を受けて手作業で接触者追跡を行う作業員をもっと雇うこと。より多くの資金をモノ作りを行う人に回すこと。

**モノ作りの方々:** 検査を作る。呼吸器を作る。病院のための個人用防護具 (PPE) を作る。検査を作る。マスクを作る。アプリを作る。抗ウイルス薬、予防薬、その他のワクチン以外の治療法を作る。ワクチンを作る。検査を作る。検査を作る。検査を作る。希望を作る。

希望を作るために恐怖を過小評価してはいけない。私たちは飛行機とパラシュートの発明家のように恐怖と希望を**協調**させるべきだ。最悪の将来に備えることが未来へを希望を私たちに与えてくれる。

真に恐れるべきは、真に恐れるべきは恐怖そのものであるとういう考え方そのものだ。
