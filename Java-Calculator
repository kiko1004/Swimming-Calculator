package com.kairospiro.swimmingcaloriescalculator;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;


import com.google.android.gms.ads.AdRequest;
import com.google.android.gms.ads.AdView;
import com.google.android.gms.ads.MobileAds;
import com.google.android.gms.ads.doubleclick.PublisherAdRequest;
import com.google.android.gms.ads.doubleclick.PublisherInterstitialAd;
import com.google.android.gms.ads.initialization.InitializationStatus;
import com.google.android.gms.ads.initialization.OnInitializationCompleteListener;

import android.os.Bundle;
import android.widget.EditText;
import android.widget.TextView;

public class Calculator extends AppCompatActivity {
    private EditText weigh;
    private EditText distance;
    private EditText minutes;
    private EditText style;
    private TextView result;
    private Button calcul;
    private PublisherInterstitialAd mPublisherInterstitialAd;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_calculator);


        MobileAds.initialize(this, new OnInitializationCompleteListener() {
            @Override
            public void onInitializationComplete(InitializationStatus initializationStatus) {
            }
        });

        MobileAds.initialize(this, "ca-app-pub-xxxxxx~xxxxxxxxx");


        mPublisherInterstitialAd = new PublisherInterstitialAd(this);
        mPublisherInterstitialAd.setAdUnitId("ca-app-pub-xxxxxxxx/xxxxxxxxxxxxx");
        mPublisherInterstitialAd.loadAd(new PublisherAdRequest.Builder().build());


        AdView adView = findViewById(R.id.adView);
        AdRequest adRequest = new AdRequest.Builder().build();
        adView.loadAd(adRequest);



        weigh = findViewById(R.id.editText3);
        distance = findViewById(R.id.editText2);
        minutes = findViewById(R.id.editText);
        style = findViewById(R.id.editText4);
        calcul = findViewById(R.id.button4);

        calcul.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {


                try {


                    String w1 = weigh.getText().toString();
                    String d1 = distance.getText().toString();
                    String m1 = minutes.getText().toString();
                    String s = style.getText().toString();


                    double w = Double.parseDouble(w1);
                    double d = Double.parseDouble(d1);
                    double m = Double.parseDouble(m1);

                    result = findViewById(R.id.result);

                    double f = 0;


                    if (s.equals("FC") || s.equals("fc")) {
                        if (d / m <= 45.72) {
                            f = 8 * w / 140 * m;
                        }

                        if (d / m >= 45.72) {
                            f = 15 * w / 140 * m;
                        }

                    }

                    if (s.equals("BC") || s.equals("bc")) {
                        if (d / m <= 35.72) {
                            f = 12 * w / 140 * m;
                        }

                        if (d / m >= 35.72) {
                            f = 23 * w / 140 * m;
                        }

                    }

                    if (s.equals("BS") || (s.equals("bs"))) {
                        f = 25;
                    }

                    if (s.equals("BF") || s.equals("bf")) {
                        if (d / m <= 25.72) {
                            f = 34 * w / 140 * m;
                        }

                        if (d / m >= 25.72) {
                            f = 36 * w / 140 * m;
                        }

                    }


                    double formula = (((6 * w) / 140) * m) + f;

                    double value = Math.round(formula);
                    String res = Double.toString(value);
                    result.setText("Great job, " + res + " kcal");
                } catch (Exception e) {
                    result.setText("Please enter valid values!");
                }
                if (mPublisherInterstitialAd.isLoaded()) {
                    mPublisherInterstitialAd.show();}


            }
        });


    }

}
