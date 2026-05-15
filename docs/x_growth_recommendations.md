# X Algorithm Growth Recommendations

_Last reviewed: 2026-05-15. Based on the current `xai-org/x-algorithm` repository in this workspace plus public X engineering context._

## What appears to drive distribution

1. **Personalized predicted engagement is the center of gravity.** The feed first builds a candidate pool, then Phoenix predicts action probabilities per candidate, and ranking converts those probabilities into a combined score. The practical implication is that content grows when it reliably causes the audience segment seeing it to favorite, reply, repost, dwell, click, share, quote, or follow the author.
2. **The system is two-stage: retrieval before ranking.** Out-of-network reach requires being retrievable by Phoenix similarity search before the ranker can score the post. In-network reach still matters because Thunder supplies recent posts from followed accounts and creates early engagement/training signals that can make later out-of-network retrieval easier.
3. **Negative feedback is an explicit downrank signal.** The scorer incorporates predicted `not_interested`, block, mute, and report probabilities with negative weights. Growth tactics that create hate-clicks, bait, mismatch, or annoyance can produce short-term impressions while teaching the model to suppress future posts.
4. **Recent user history shapes recommendations.** Query hydration includes action sequences, followed users, followed/inferred topics, starter packs, impressions, served history, social graph signals, demographics, IP, and gender inference. Creator strategy should therefore optimize for consistent audience-topic fit, not generic virality.
5. **Eligibility and freshness gates matter before quality can win.** Candidates can be removed for duplicates, old posts, self-posts, retweet duplication, subscriptions, previously seen/served items, muted keywords, author social graph blocks/mutes, video constraints, topic constraints, and visibility filtering.
6. **Video/media can help only when eligible and watched.** The scorer only applies the video-quality-view weight when video duration passes the minimum duration check, while ranking also considers dwell-related predictions. Media should increase comprehension and watch time, not exist as decoration.
7. **Diversity mechanisms prevent one author or one conversation from monopolizing the feed.** Author diversity attenuates repeated posts by the same author in a response, and post-selection filters deduplicate conversations. One excellent post per topic cluster is usually better than flooding many similar posts.
8. **Post-selection safety and ads blending can reshape the final feed.** Visibility, ancillary visibility, conversation deduplication, brand-safety hydration, and ad blending happen after scoring/selection, so content must remain safe, unambiguous, and advertiser-compatible to preserve reach.

## Concise growth recommendations

1. **Pick a narrow audience-topic wedge and repeat it.** Publish mostly within 2-4 recognizable topic lanes so Phoenix can associate your profile, followers, engagers, and post embeddings with a stable audience.
2. **Design for replies first, then shares/reposts, then favorites.** End posts with a concrete prompt, ask for experience-based answers, compare two options, or make a claim knowledgeable people can extend. Avoid empty engagement bait.
3. **Earn dwell with fast structure.** Put the key promise in the first line, use short paragraphs, include a useful example/table/list, and make media explain something faster than text alone.
4. **Create save/share-worthy originals.** Publish frameworks, checklists, contrarian-but-supported observations, data snippets, templates, and before/after breakdowns that followers would send to colleagues or quote with commentary.
5. **Seed the right in-network audience.** Build and interact with a follower graph that matches your topic wedge; reply thoughtfully to adjacent creators; avoid chasing off-topic engagement that teaches the model the wrong audience.
6. **Minimize negative-feedback risk.** Do not overpost, mislead in hooks, post repetitive threads, disguise ads, overuse outrage, or force divisive topics unrelated to your wedge. These behaviors raise predicted not-interested, mute, block, or report risk.
7. **Use video intentionally.** If using video, make it long enough to be eligible for video-quality-view scoring, open with immediate context, add captions/visual proof, and optimize for completion or meaningful watch time.
8. **Avoid eligibility landmines.** Keep posts fresh, original, non-duplicative, accessible, brand-safe, and free of terms your target audience commonly mutes. Do not rely on quote/repost chains that may be deduplicated.
9. **Post fewer, stronger candidates.** Because repeated-author scoring decays within a feed response, prioritize 1-3 high-signal posts per day over bursts of similar updates.
10. **Measure by audience-quality signals, not raw impressions.** Track reply quality, repost-to-like ratio, profile visits/follows per post, dwell proxies such as long-form expansions or video completion, negative replies, unfollows, and muted-topic complaints.

## Operating cadence

- **Weekly:** Review top posts by replies, reposts, follows, and low negative feedback; identify which topic/audience pair worked.
- **Biweekly:** Run one format experiment at a time: hook style, media type, post length, question type, or publishing window.
- **Monthly:** Prune off-topic series, double down on the 2-3 formats that generate qualified replies and shares, and update a topic map of accounts your best engagers also follow.

## Bottom line

The safest growth strategy is not to “hack” one static weight. It is to become highly predictable to the recommendation system for a valuable audience: publish original posts in a narrow domain, trigger high-quality replies/shares/dwell, build a matching follower graph, and avoid negative feedback or eligibility filters.
