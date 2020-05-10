
- Perception Markup Language was\cite{sauce:perceptionML} proposed to allow simpler mixing of components
	- demonstrates desirablity of improved component tooling
	- more standard connections, easier to add and remove components
- builds a standard langugead for compoents to communicate
	- doesn't specify how the compobents behave, just how they structure their speech
- protocols don't exist/enforced just a message data type
	- Joachim Parrow proovides "An Introduction to the pi-Calculus" in \cite{bergstra2001handbook} which describes "protocol calculus" some way to do this
- this standardisation allows componetns to exchange information in an agreed way
- seek to build on this concept, if not this implementation
	- would like to explore using XML schema to generate interfaces, but, we use PFP langauge constructs as type checked equivalent
	- PFP is checked at compile time, though, it's inevitably limited to the language in question
	- our approach doesn't have a way to embed the transformational cocept from protocol calculus


@inproceedings{
	sauce:perceptionML,
		address = {Santa Cruz, CA},
		title = {Perception {Markup} {Language}: {Towards} a {Standardized} {Representation} of {Perceived} {Nonverbal} {Behaviors}},
		url = {http://ict.usc.edu/pubs/Perception%20Markup%20Language-%20Towards%20a%20Standardized%20Representation%20of%20Perceived%20Nonverbal%20Behaviors.pdf},
		abstract = {Modern virtual agents require knowledge about their environment, the interaction itself, and their interlocutors' behavior in order to be able to show appropriate nonverbal behavior as well as to adapt dialog policies accordingly. Recent achievements in the area of automatic behavior recognition and understanding can provide information about the interactants' multimodal nonverbal behavior and subsequently their a?ective states. In this paper, we introduce a perception markup language (PML) which is a ?rst step towards a standardized representation of perceived nonverbal behaviors. PML follows several design concepts, namely compatibility and synergy, modeling uncertainty, multiple interpretative layers, and extensibility, in order to maximize its usefulness for the research community. We show how we can successfully integrate PML in a fully automated virtual agent system for healthcare applications.},
		booktitle = {The 12th {International} {Conference} on {Intelligent} {Virtual} {Agents} ({IVA})},
		author = {Scherer, Stefan and Marsella, Stacy C. and Stratou, Giota and Xu, Yuyu and Morbini, Fabrizio and Egan, Alesia and Rizzo, Albert and Morency, Louis-Philippe},
		month = sep,
		year = {2012},
		keywords = {Virtual Humans}
	}





XML is text

DSL for constructiong valid XML?

- no compile time checks :(
- might be "self-validating" because it's checked as it's built rather than as a post-build step?


		val fooDoc =
			XMLDSL("foo doc") {
				root =>
					root("foo") { _
						.attribute[Int]("het")
						.child("bar") { _  }
					}
			}

			fooDoc ("foo") { _
				.c("bar")()
			}

			fooDoc ("foo") { _
				.a("het", 3)
				.c("bar")()
			}

the PML seems to be ... a thing ... and it goes everywhere that BML and FML didn't

tried to speed up usages and developinemnt embrace/copying naming and conventions from existing ones of;
- VoiceXML; https://www.w3.org/TR/voicexml30/
- EmotionML; https://www.w3.org/TR/emotionml/
- BML
- FML

the model can handle uncertainty as well as the layered complexisty of this, and remains extensible

used "CMU's PocketSphinx" and ... didn't hate it?

mentions another SSI kit

concludes that

> "
> In the long run, PML will enable collaborations between currently often isolated
> workgroups as well as increase the reusability of previous findings and
> implementations.
> "
